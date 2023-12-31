# 6주차 원자력 상태 판단
본 과제는 원자력 데이터가 주어질 때 상태를 분류하는 문제 입니다.
본 과제는 심층신경망 I 을 기반으로 원자력발전소 상태를 판단하여 베이스라인을 넘기시면 됩니다.
주어진 데이터를 이용하여 원자력발전소의 상태을 예측하는 문제입니다.
## DNN을 이용한 원자력 상태 판단
본 과제에서는 수업시간에 배운 DNN을 이용하여 1차원 원자력 상태 판단를 분류합니다
## 코멘트
현재 베이스라인은 SGD optimizer를 사용한 결과입니다. 하지만 기존 베이스라인과 overview에서는 Standard Scaler와 Adam optimizer 사용했었기 때문에 두 라이브러리를 사용한다 해서 문제가 되지 않는다는 점 알려드립니다.

# 6주차 기상정보를 이용하여 태양광 발전량 예측하기
![Alt text](image.png)

* 본 과제는 기상정보를 이용하여 태양광 발전량을 예측하는 문제입니다. 주어지는 기상정보 데이터에 대한 정보는 상단의 Data탭을 참고해주세요.
* 본 과제는 실습1, 실습2, 실습3 및 이론강의, 실습강의을 참고하여 10/10일 까지 완료해야하는 6주차 실습문제 2번 입니다.
* 본 과제에서는 💥 반드시 6주차에 배운 NN방법론만을 사용💥하여야 합니다. 그 외의 다양한 회귀방법론의 사용을 금합니다.
* 리더보드에 있는 NN_Baseline 점수를 넘기셔야 합니다.
NN_Baseline은 sklearn의 StandardScaler를 사용하여 전처리 하였으며, 4개의 Linear Layer와 Sigmoid 함수를 쌓아서 10에포크 학습하여 구성하였습니다. 정답이 존재하는 것은 아니며, Learning Rate, Linear Layer의 형태 및 갯수 등은 직접 실험을 통해서 찾아보시기 바랍니다.
* 해당 문제는 데이터의 갯수가 조금 큰편이라 학습하는데 시간이 꽤 걸릴 수 있습니다. (보통 5분 이내)
* 분류문제가 아닌 회귀문제임에 유의해주세요.
* 회귀문제임으로 loss는 MSELoss를 사용해주세요.

## 베이스라인 정보
* baseline1: 15.38268
  * 실습3과 동일하게 모델을 설계할 경우 10epoch 학습했을 때 나오는 성능입니다.

* baseline2: 10.33854
  * 파라미터를 조정하여 베이스라인 2를 달성해보시기 바랍니다.
  * 
베이스라인 1을 넘기시면 베이스라인 달성으로 인정됩니다.

## Evaluation
![RMSE](https://blog.kakaocdn.net/dn/b10oWd/btqBxATyHHi/QWuTvEd3FBMh5BfmkUVVCk/img.png) 

평가는 Regression에서 많이 사용되는 Root Mean Square Error (RMSE) 스코어를 기준으로 함. 해당 식은 위와 같음.