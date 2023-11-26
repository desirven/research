GLIDE: Towards Photorealistic Image Generation and Editing with Text-Guided Diffusion Models
==
### ICML 2021

Text-to-Image Generation Task에서 Diffusion을 제대로 사용한 첫 논문이다.
OpenAI 논문으로 기존에 Dalle(v1)에서는 vae 기반이였는데 이 논문에서 Diffusion을 사용하였고, 이후 Dalle v2가 Diffusion을 사용하도록 바뀌게 한 논문이다.



### CLIP Guidance

이 당시 CLIP이 나오면서 (2103) GAN에서 Discriminator로 CLIP을 사용하는 연구들이 있었다.

그래서 이 논문 (2112) 에서는 DIffusion에서 Discriminator을 사용하는 Guided Diffusion에 CLIP을 적용하는 실험을 진행한다.

![수식](./src/1.png)

Classifier 부분을 CLIP의 similarity를 사용한 Classification으로 대체한 것이다.

기존 CLIP과의 차이점이라면  Guided Diffusion에서는 이미지가 아니라 중간 노이즈를 입력으로 넣기 때문에 이에 대한 추가적인 학습이 필요하다. (기존 CLIP입장에서 중간 노이즈 이미지는 OOD라고 표현한다.)



### Training
method 대신 Training 장으로 되어있다.
모델은 parameter가 3.5B인 64x64모델이랑, 1.5B인 256x256 upsampling 모델을 사용했다.
(확인해보니 LDM과 같은 날짜에 arxiv에 등록되었다.)

#### Text-Conditional Diffusion Models
텍스트 인코더는 트랜스포머로 이루어져 있다. 각 k, v를 인코딩할 때 입력

(여기에서 텍스트는 condition으로 들어가는 것이다. 위에 말한 CLIP Guidance는 guide를 하기 위한 것으로 둘의 목적이 다르다.)



#### Fine-tuning for classifier-free guidance
학습을 하고 난 후에 문장 내에서 20%를 랜덤하게 empty sequence로 바꾸어서 fine tuning해준다.

(기존 cfg는 text condition을 고려하는 task가 아니기 때문에 추가된 것으로 보인다.)



#### Image Inpainting
기존 방법 1 - (Score-based, SDEdit)
단순하게 생성하면서 마스크 외부 영역을 q(xt​ ∣ x0​)로 바꾸면서 생성한다.
학습할때 inpainting을 고려하지는 않는다.

기존 방법 2 - (Palette)
학습할 때 랜덤하게 마스킹하고, 노이즈를 씌우고 해당 영역을 랜덤 노이즈로 시작함
입력 : 마스킹된 RGB

GLIDE
Palette와 동일한 방법으로 학습함.
입력 : 마스킹된 RGB + 원본 RGB + 마스크 채널 > 7채널
추가된 파라미터는 0으로 초기화
![수식2](./src/2.png)

Noised CLIP models
Classifier로 CLIP을 사용하기 위해서 noised image도 학습한다.
64x64를 입력으로 넣어서 학습한 것이다
<img src="./src/3.png" width="50%">

<img src="./src/4.png" width="50%">
