# 딥러닝 스터디

### 딥러닝 관련 스터디(2020.03~진행중)

------------
__팀원__ : 류지혜[jihyejjang](https://github.com/jihyejjang), 이지민[Jimin980921](https://github.com/Jimin980921), 한나연[HanNayeoniee](https://github.com/HanNayeoniee)

__목차__ : 

- [MNIST예제를 이용한 다중분류](#--mnist예제를-이용한-다중분류)

- [CNN을 이용한 과일 분류(사과, 바나나, 오렌지, 혼합)](#--cnn을-이용한-과일-분류)

- [CNN을 이용한 과일 분류(사과, 바나나, 오렌지, 혼합)의 improved version](#--cnn을-이용한-과일-분류-improved-version)

- [tensorflow api를 이용한 object detection](#--tensorflow-api를-이용한-object-detection)

----------------------
__각 목차에 해당하는 코드 요약__:


##### - MNIST예제를 이용한 다중분류
> 데이터셋: keras mnist 사용(train set 갯수: 60000, test set 갯수: 10000)              
![다운로드](https://user-images.githubusercontent.com/47767202/77398775-77085b80-6deb-11ea-82d5-78da08062a96.png)                   
> 최종목표: 다중분류 -> 맨 마지막 출력층의 activation function은 softmax   
> optimizer는 sgd, loss는 categorical_crossentropy                
> test set accuracy 94.21%

<br><br><br>



##### - CNN을 이용한 과일 분류                                    
> 데이터셋: https://www.kaggle.com/mbkinaci/fruit-images-for-object-detection                         
> 참고커널: https://www.kaggle.com/prateek0x/multiclass-image-classification-using-keras             
![다운로드](https://user-images.githubusercontent.com/47767202/77398531-0e20e380-6deb-11ea-9680-c2a92db9d073.png)                     
> 최종목표: 다중분류 -> 맨 마지막 출력층의 activation function은 softmax                  
> optimizer는 adam, loss는 categorical_crossentropy                            
> test set accuracy 61.7%                                  
> 부족한점: 데이터셋이 너무 적어 validation set을 만들지 않음, overfitting이 일어난 것으로 예상, 결과적으로 낮은 성능            
> 해결방안: image generator 로 이미지 수 최대한 늘리고 validation set을 만든 다음, 더 큰 네트워크 구성           
> 문제점: 데이터셋 자체의 문제(순수한 과일 사진이 아닌 일러스트 이미지나 다른 물체와 함께 있는 사진이 있었음)         
> 문제사진:
> 


<br><br><br>

##### - CNN을 이용한 과일 분류 improved version
> 데이터셋: https://www.kaggle.com/mbkinaci/fruit-images-for-object-detection (위와 동일)                      
> 모델구성과 하이퍼파라미터 등의 조건은 대부분 위와 동일(epoch수는 70으로 늘림)                  
> 바뀐 점: 부족한 데이터셋을 해결하기 위해 data augmentation을 이용해 데이터 수를 늘리고 validation set 또한 구성함                 
> test set accuracy 75%                                               
> 부족한점: train : val : test set의 비율이 맞지 않음.                                 

<br><br><br>

##### - tensorflow api를 이용한 object detection
> 데이터셋: https://www.kaggle.com/mbkinaci/fruit-images-for-object-detection (위와 동일)                
> 참고자료: https://musma.github.io/2019/02/15/tensorflow-on-windows.html                        
> 
