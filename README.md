# AI
딥러닝 평가 : 실제값 y와 예측값y언더바 차이가 얼마나 차이가 나는지로 평가
cost function : 실제값과 예측값의 차이구하는 함
cost function의 최소값이 찾는것이 주목적
1.Gradient descent 경사하강법 : cost function 은 2차함수이므로 미분했을떄 미분계수 0인지점에서 극소점을 가진다
해당 극소점에 해당하는 값을찾으면 그값이 최적화된 weight 값
Gradient descent 문제점 : 
1) 데이터양이 많을경우 학습속도가 느리다
2) local minimum 문제에 빠질수있다 global minimum을 구해야하는데 지역최소값에 갇쳐 나오지못하는 현상발새
3) plateau 현상 : 특정구간 기울기가 완만한구간에서 학습속도가 느려지는 현상이 발생할수있음
4) zigzag : 일변량 함수일떄는 변수하나에 대한 기울기통해 찾는데 다변량 함수일때는 여러변수의 각 기울기학습을 하므로, 만약 w1 , w2의 기울기가 다르면 기울기 학습이 지그재그로 효율적이지 못할 가능성이있음

2.Epoch
모든 훈련Dataset을 학습한 횟수
ex) 1 Epcoh 를 학습햇다면 주어진 train set을 모델에 모두 한번씩 훈련함

3.batch
1개의 Epoch의 여러개의 batch 존재 , batch는 한번연산할때 훈련시키는 data양, batch가 너무 크면 속도가 느리고 메모리문제가 발생할수있음, batch 가 너무작으면 속도는 빠르지만 가중치를 자주 학습하는 문제가 발생
1개의 epoch가 10개의 mini-batch로 구성

4.iteration
전체 dataset을 train 시키는데 필요한 batch 수

5.Batch Gradient descent 배치 경사 하강법
기존 경사하강법과 달리 batch단위의 경사하강법을 통해 batch안의 데이터를 대상으로 경사하강법을 진행하므로 안정적으로 수렴함
그러나 train dataset이 커지면 시간과 리소스 소모가 커짐.

6.Stochastic Gradient descent 확률적 경사하강법
train data set에서 무작위로 샘플을 하나 추츨하여 그 샘플에대한 기울기를 계산 -> 학습속도가 빠름, 메모리 소모량 적음
그러나 무작위 샘플에 대한 기울기를 구하므로 불안정하게 움직임
최적해에 근접하게 움직이지만 global minimum에 도달하지 못할 가능성존재함.

7.mini-batch gradient descent 미니 배치 경사 하강법
배치 크기를 줄이고 확률적 경사 하강법을 사용함
학습속도가 빠름
