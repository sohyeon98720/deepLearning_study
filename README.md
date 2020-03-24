# 딥러닝 스터디

### 딥러닝 관련 스터디(2020.03~진행중)

------------
__팀원__ : 류지혜[jihyejjang](https://github.com/jihyejjang), 이지민[Jimin980921](https://github.com/Jimin980921), 한나연[HanNayeoniee](https://github.com/HanNayeoniee)

__목차__ : 

- [MNIST예제를 이용한 다중분류](#mnist예제를-이용한-다중분류)

- [CNN을 이용한 과일 분류(사과, 바나나, 오렌지, 혼합)](#cnn을-이용한-과일-분류)

----------------------
__각 목차에 해당하는 코드 요약__:


###### `MNIST예제를 이용한 다중분류` 
> 데이터셋: keras mnist 사용(train set 갯수: 60000, test set 갯수: 10000)              
![다운로드](https://user-images.githubusercontent.com/47767202/77398775-77085b80-6deb-11ea-82d5-78da08062a96.png)                   
> 최종목표: 다중분류 -> 맨 마지막 출력층의 activation function은 softmax   
> optimizer는 sgd, loss는 categorical_crossentropy                
> test set accuracy 94.21%





###### `CNN을 이용한 과일 분류`                                    
> 데이터셋: https://www.kaggle.com/mbkinaci/fruit-images-for-object-detection                         
> 참고커널: https://www.kaggle.com/prateek0x/multiclass-image-classification-using-keras             
![다운로드](https://user-images.githubusercontent.com/47767202/77398531-0e20e380-6deb-11ea-9680-c2a92db9d073.png)                     
> 최종목표: 다중분류 -> 맨 마지막 출력층의 activation function은 softmax                  
> optimizer는 adam, loss는 categorical_crossentropy                            
> test set accuracy 61.7%                                  
> 문제점: 데이터셋이 너무 적어서 validation set 을 만들지 않음.              
> 문제점: validation set이 없어 정확한 판단 X(overfitting 등)                             
> 해결방안: image generator 로 이미지 수 최대한 늘리고 validation set을 만든 다음, 더 큰 네트워크 구성                  
