# What is Deep Learning?

## 1. AI: artificial intelligence
![AI](https://user-images.githubusercontent.com/96757866/156586954-95b904e8-e7ef-4b03-9e15-37e0e7eddddb.png)   
*출처 : https://brunch.co.kr/@gdhan/10* 

## 2. Machine learning techniques
![Machine Learning Map](https://user-images.githubusercontent.com/96757866/156589721-dcc5587c-0c05-4714-a3f3-f78f8632741a.png)
*출처 : https://gitplanet.com/project/machine-learning-octave*

(1) Superviser learning
- classification
- regression   

(2) Unsuperviser learning
- clustering
- dimension reduction
- representation learning
- data generation
- association rule
- collaborative filtering   

(3) Reinforcement learning
- sequential decsion problem

## 3. Advantages and Limitations of Deep Learning
(1) Advantages
- 함수를 근사하는 능력이 뛰어나다.
- 특징을 자동으로 추출한다.
- 모델의 확장성이 뛰어나다.
- 기존 머신러닝보다 훨씬 좋은 성능을 보인다.

(2) Limitations
- 딥러닝 모델은 파라미터가 많기 때문에 다른 머신러닝 모델보다 상대적으로 많은 학습 데이터가 필요하다.
- 딥러닝 모델은 훈련을 위한 시간과 비용이 많이 든다.
- 딥러닝 모델에는 설정 파라미터가 많아서 최적의 모델과 훈련 방법을 찾으려면 상당히 많은 검색 시간과 튜닝 시간이 필요하다.
- 인공 신경망 모델은 오류를 파악하거나 디버깅하기 어렵다.
- 지도 학습에서는 타깃 데이터를 만들 때 드는 비용이 만만치 않다.

## 4. Perceptron
(1) 개념
- 스스로 문제에 맞춰 학습하는 인공 신경망 모델
- 새로운 입력에 대한 오차가 발생하면 뉴런의 연결 강도를 조절하는 방식

(2) 구조
- 입력 데이터가 들어오면 가중치와 곱해서 가중 합산을 함
  => 결과가 0보다 크면 1출력, 그렇지 않으면 0 출력   
- 가중 합산과 계단 함수를 순차적으로 실행
![image](https://user-images.githubusercontent.com/96757866/156602214-5b3398ed-53e2-4bfa-851b-6182b8bfaa22.png)
*출처 : https://hleecaster.com/ml-perceptron-concept/*

- 퍼셉트론은 두 종류의 클래스를 직선으로 분류하는 선형 분류기(linear classifier)
- 입력 데이터와 가중 합산 식은 두 클래스를 분류하는 결정 경계(decision boundary)를 이룸   
  => $ W_1x_1+W_2X_2+b=0 $
![image](https://imgur.com/otA0O3u.gif)
*출처 : https://imgur.com/otA0O3u*


| |FNN|CNN|RNN|GNN|
|---|---|---|---|---|
|Full name|Feedforward Neural Network|Convolution Neural Network|Recurrent Neural Network|Graph Neural Network|
|가정사항|없음|공간 데이터 가정|순차 데이터 가정|그래프 데이터 가정|
|연결|순방향 연결만 갖음||출력 데이터가 다시 입력되는 피드백 연결 가짐||

## Reference
1. Do it! 딥러닝 교과서
