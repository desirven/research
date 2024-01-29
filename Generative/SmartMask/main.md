SmartMask: Context Aware High-Fidelity Mask Generation for Fine-grained Object Insertion and Layout Control
===
arxiv 23.12, adobe

Inpainting에서 text prompt는 객체의 의미를, mask는 위치와 크기를 제어한다.  
하지만 대부분 방법들은 coarse-mask를 사용한다. (bbox)  
하지만 이러한 경우 배경 영역이 포함되기 때문에 배경이 변경된다.  
이를 막으려고 scribble을 사용하지만 사람과 같이 세부정보가 많은 객체는 coarse-scribble로는 힘들다.  
게다가 새로운 장소에서는 그 장소에 어울리는 마스크를 만들어줘야 한다.  
  
* 초보 사용자도 배경 보존이 우수한 세밀한 객체 마스크를 생성할 수 있는 SmartMask를 제안한다.  
* 심지어 마스크 없이도 가능하다.  
* SmartMask를 반복적으로 사용하여 더 높은 품질의 출력을 생성할 수 있다.  

## Method
이 논문에서 하고 싶은 것은 T_obj(객체 설명 text)과 T_context(결과 이미지 설명 text)를 기준으로 마스크 M_obj를 예측하는 것이다.  
이 후 이 마스크를 ControlNet-Inpaint에 입력한다.  

![img.png](img.png)  

### SmartMask for Mask-Free Object Isertion
> Sematic Amodal Segmentation Data : 가려진 영역에 대한 정보까지 가지고 있는 데이터, 순서가 정해져있음  

![img_1.png](img_1.png)  
레이어를 쌓아서 인코더를 통해서 feature를 뽑고, 두개에 텍스트와 함께 디노이징한다.  
결국 다음 순번의 객체 마스크가 포함된 마스크를 예측하도록 학습한다.  
> 역시 adobe라 그런지 코드도 없고 중요한 설명을 숨겼다.  
> 치사하게도 condition이 3개나 되는데 어떻게 들어가는 건지에 대한 설명이 하나도 없다...  
> 심지 어 그 흔한 "The code will be available soon"이 적힌 레포지토리도 없다...  
  
> 상식적인 선에서 예상해보자면  
> ebedding된 feature는 기존 inpainting처럼 concat했거나 ControlNet으로 들어갔을 것 같고  
> 텍스트는 [bos] 토큰같은 것 사이에 두고 concat해서 cross-attention에 들어가지 않았을까 싶다...  
  
### Data Augmentation for Precise Mask Control  
![img_2.png](img_2.png)  
G_obj 유저가 입력으로 준 마스크이다.  
해당 영역을 기준으로 객체에 최종 마스크를 예측하도록 학습한다.  
a = 0.7이라고 한다.  
> 진짜 너무 불친절하다.  
> G가 입력 마스크라고 하는데 마스크 내부가 1이고 외부가 0이다. 그래야 말이 된다.  
  
> 그리고 G를 따로 임베딩 해주지 않는 것을 보니 일반적인 Inpainting방법인 것이 맞는 것 같다.  
> 위 overview에서 encoder는 LDM의 encoder가 맞는 것 같고 S_k와 G를 Inpainting처럼 concat해서 넣어주는 것 같다.  
   
![img_3.png](img_3.png)  
  
4가지 케이스에 대해서 시나리오를 세우고 학습한다. 
1. 마스크 입력이 없는 경우  
    여기서 G는 전체가 0으로 사용한다고 한다. 
2. bbox 입력  
    GT를 기준으로 bbox를 만든다.
3. coarse spatial guidance  
    gaussian blob을 사용한다.  
    gaussian blob은 찾아보니 그림처럼 점점 그라데이션되는 형태이다.   
4. scribble  
    그냥 사용했다고 한다. 학습용 마스크를 어떻게 만들었는지 설명이 없다.  
    확장했다고 하는데, 어느정도 파라미터로 확장했는지 설명해줬으면 좋을텐데...
  
이를 통해 추론시 어떤 형태의 유저 입력 마스크가 들어와도 대응할 수 있다고 한다. 
  
### Global Planning for Multi-step Inference  

