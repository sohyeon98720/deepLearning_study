# 딥러닝 스터디

### 딥러닝 관련 스터디(2020.03 ~2020.04)

------------

__목차__ : 

1.   [MNIST예제를 이용한 다중분류](#--mnist예제를-이용한-다중분류)

2.   [CNN을 이용한 과일 분류(사과, 바나나, 오렌지, 혼합)](#--cnn을-이용한-과일-분류)

2-1. [CNN을 이용한 과일 분류(사과, 바나나, 오렌지, 혼합)의 improved version](#--cnn을-이용한-과일-분류-improved-version)

3.   [tensorflow api를 이용한 object detection](#--tensorflow-api를-이용한-object-detection)

3-1. [xml을 이용한 object detection](#--xml을-이용한-object-detection)

4.   [semantic segmentation을 이용한 배경합성](#--semantic-segmentation을-이용한-배경합성pytorch)

4-1. [instance segmentation](#--instance-segmentationkeras)

----------------------
__각 목차에 해당하는 코드 요약__:


##### - MNIST예제를 이용한 다중분류
데이터셋: keras mnist 사용(train set 갯수: 60000, test set 갯수: 10000)              
![다운로드](https://user-images.githubusercontent.com/47767202/77398775-77085b80-6deb-11ea-82d5-78da08062a96.png)                   
최종목표: 다중분류 -> 맨 마지막 출력층의 activation function은 softmax   
optimizer는 sgd, loss는 categorical_crossentropy                
test set accuracy 94.21%

---------------------

##### - CNN을 이용한 과일 분류                                    
데이터셋: https://www.kaggle.com/mbkinaci/fruit-images-for-object-detection                         
참고커널: https://www.kaggle.com/prateek0x/multiclass-image-classification-using-keras             
![다운로드](https://user-images.githubusercontent.com/47767202/77398531-0e20e380-6deb-11ea-9680-c2a92db9d073.png)                     
최종목표: 다중분류 -> 맨 마지막 출력층의 activation function은 softmax                  
optimizer는 adam, loss는 categorical_crossentropy                            
test set accuracy 61.7%                                  
부족한점: 데이터셋이 너무 적어 validation set을 만들지 않음, overfitting이 일어난 것으로 예상, 결과적으로 낮은 성능            
해결방안: image generator 로 이미지 수 최대한 늘리고 validation set을 만든 다음, 더 큰 네트워크 구성  
<br>
문제점: 데이터셋 자체의 문제(순수한 과일 사진이 아닌 일러스트 이미지나 다른 물체와 함께 있는 사진이 있었음)         
문제사진예시:                                            
<img src="https://user-images.githubusercontent.com/47767202/78045953-88380600-73b1-11ea-89e3-9dc483e31385.jpg" width="30%">        
<img src="https://user-images.githubusercontent.com/47767202/78046380-0ac0c580-73b2-11ea-972d-344382e0a6d3.jpg" width="30%">     

---------------

##### - CNN을 이용한 과일 분류 improved version
데이터셋: https://www.kaggle.com/mbkinaci/fruit-images-for-object-detection (위와 동일)            
![다운로드](https://user-images.githubusercontent.com/47767202/77398531-0e20e380-6deb-11ea-9680-c2a92db9d073.png)     
모델구성과 하이퍼파라미터 등의 조건은 대부분 위와 동일(epoch수는 70으로 늘림)                  
바뀐 점: 부족한 데이터셋을 해결하기 위해 data augmentation을 이용해 데이터 수를 늘리고 validation set 또한 구성함                 
test set accuracy 75%                                               
부족한점: train : val : test set의 비율이 맞지 않음              
문제점: 위와 동일              

-------------

##### - tensorflow api를 이용한 object detection
데이터셋: https://www.kaggle.com/mbkinaci/fruit-images-for-object-detection (위와 동일)          
<img src="https://user-images.githubusercontent.com/47767202/78047593-8111f780-73b3-11ea-8668-387470b01ec9.PNG" width="30%">     
참고자료: https://musma.github.io/2019/02/15/tensorflow-on-windows.html                        
부족한점: 데이터셋에서 제공하는 xml파일을 이용하여 object detection을 하자는 기존 목표에서 벗어남           

------------

##### - xml을 이용한 object detection
데이터셋: https://www.kaggle.com/mbkinaci/fruit-images-for-object-detection (위와 동일)                 
__캐글링크__: https://www.kaggle.com/sohyeonee/fruit-objectdetection-xml                                          
<img src="https://user-images.githubusercontent.com/47767202/78454074-bd559880-76d0-11ea-8224-bb5d2c3a19f7.PNG" width="30%">

-----------

##### - semantic segmentation을 이용한 배경합성(pytorch)
입력영상(인물,배경 순):                               
  <img src="https://user-images.githubusercontent.com/47767202/80336132-5c654e80-8891-11ea-97c9-88fa09e1ca11.jpg" width="30%">
  <img src="https://user-images.githubusercontent.com/47767202/80336171-7f8ffe00-8891-11ea-9c86-4a75f5e2a58c.jpg" width="37.5%">      
출력영상(인물+배경 합성영상):                          
  <img src="https://user-images.githubusercontent.com/47767202/80336526-75baca80-8892-11ea-980f-924a90980b03.JPG" width="31%">         
참고자료: https://github.com/kairess/semantic-segmentation-pytorch

-----------
##### - instance segmentation(keras)                                    
참고자료: https://towardsdatascience.com/computer-vision-instance-segmentation-with-mask-r-cnn-7983502fcad1
