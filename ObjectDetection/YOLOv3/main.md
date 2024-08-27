YOLOv3: An Incremental Improvement
===
arxiv 2018
####
figure 참고 : https://ffighting.net/deep-learning-paper-review/object-detection/yolo-v3/
####
### Introduction 
큰 향상의 연구는 하지 않았고, 간단한 tech report이다.

### Bounding Box Prediction
![img.png](img.png)  
기존에는 모델이 예측한 offset을 bbox좌표로 변환해서 loss에 사용하였는데, 예측한 값을 그대로 사용하는 것으로 변경  
![img_1.png](img_1.png)

### Class Prediction
box의 내부가 multilabel일 경우, softmax를 sigmoid로 바꾸어서 BCE로 loss를 사용하는 것이 더 타당하다.  
![img_2.png](img_2.png)                                                                 
![img_3.png](img_3.png)
![img_4.png](img_4.png)

### Predictions Across Scales
* FPN처럼 중간 레벨의 feature도 사용한다.
* COCO 데이터셋에서 미리 bbox크기를 클러스터해서 9개의 클러스터와 3개의 스케일을 미리 뽑았고 이를 앵커로 사용한다.

### Feature Extractor
* 기존 DarkNet-19에서 깊이를 증가하고 shortcut을 추가해서 DarkNet-53을 만들었다.
![img_5.png](img_5.png)

### Results

<img alt="img_6.png" src="img_6.png" width="80%"/>

<img alt="img_7.png" src="img_7.png" width="80%"/>
