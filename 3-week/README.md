# 3주차 날씨정보를 이용해 배추 가격을 예측하기
본 과제는 특정일의 평균기온, 최저기온, 최대기온, 강수량 데이터가 주어질때, 배추가격을 예측하는 문제 입니다. 본 과제는 선형회귀 실습3을 기반으로 배추가격을 예측하여 베이스라인을 넘기면 됩니다.

## 목표
해당 데이터 셋은 배추 가격에 대한 날짜, 평균기온, 최저기온, 최고기온, 강수량을 확인할 수 있습니다.
위에 언급한 배추가격과 관련된 정보들을 통하여 해당 배추의 가격을 예측하는 것이 해당 실습의 목표입니다.



# 3주차 자동차 가격 예측
본 데이터 셋은 kaggle open dataset으로, 영국의 중고차량 정보들로 구성되어있습니다.

## 목표
해당 데이터 셋은 중고 차량에 대한 가격, 변속기, 마일리지, 연료 유형, 도로세, 갤런당 마일리지(mpg), 제조회사 및 엔진 크기 등을 확인할 수 있습니다.
위에 언급한 차량의 정보들(제조회사, 엔진크기, 변속기 등)을 통하여 해당 차량의 가격을 예측하는 것이 해당 실습의 목표입니다.

대부분의 항목들이 데이터 실수화가 되어있지만, 일부 항목은 데이터 실수화가 되어있지 않습니다. sklearn에서 제공하는 LabelEncoder 함수를 통해 데이터 실수화를 진행하신 다음, 수업시간에 배운 인공지능 방법론을 통해 문제를 풀으시면 됩니다.

본 문제의 평가 방식은 MAE(Mean Absolute Error)입니다. 모델을 학습할 때 다른 Cost function을 사용하셔도 상관은 없으나 원활한 진행을 원하시면 MAE 방식을 사용하시길 권장합니다.

수업 시간에 배운 선형 회귀를 통해서만 베이스라인을 통과하셔야 합니다. 그 외에 다른 모델(MLP, KNN, RandomForest 등)을 사용하여 통과한 베이스라인은 인정 안 됩니다.