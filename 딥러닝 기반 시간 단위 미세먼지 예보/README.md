# 딥러닝 기반 시간 단위 미세먼지 예보 Air-Check <br/>

## 1장. 주제 탐색 과정

#### 개발 기간 
2022.09 ~ 2022.10 (4주)
<br/>

#### 개발 환경
- Python 3.6.8 
- Jupyter notebook
  
#### 주제 
: 시간 단위로 미세 먼지 수치를 예보하자. <br/>
- 미세 먼지로 인해 사람들의 외부활동이 제한된다.
- 현재의 미세먼지 예보는 '예보'가 아닌 '통보'이다.

#### 데이터 수집 및 전처리
##### 데이터 수집
- 공공데이터포털 : 한국언론진흥재단_뉴스빅데이터_메타데이터_미세먼지

##### 데이터 전처리 
- '선릉역' 데이터로 train set, 나머지 데이터로 test set 생성

<img src="https://github.com/kyounggseo/perconal-projects/assets/102573192/7e739d8b-1fa6-46f8-b94a-71231f7d4842" width="30%" height="70%"> <br/>
- 분 -> 시간 단위 평균으로 재구성

#### 분석 모델링
- n_steps 최적값으로 '5' 사용 (n_steps가 낮으면 정확도가 감소하고, 높으면 효율성이 감소하는 경향이 있음)
- 5시간 과거데이터로 1시간 미래의 미세먼지를 예측
<br/>

## 2장. 분석결과
### 1. 강남역 엔제리너스 데이터 예측 결과
<img src="https://github.com/kyounggseo/perconal-projects/assets/102573192/7ade2bc9-ba5e-4b61-8b30-270fb99461a4" width="80%" height="70%"> <br/>
- PM10 평균 오차(RMSE) = 9.17
- PM2.5 평균 오차(RMSE) = 6.70
<br/>

### 2. 강남역 역삼공원 데이터 예측 결과
<img src="https://github.com/kyounggseo/perconal-projects/assets/102573192/d2902875-5060-4c1f-ac16-a34c8d689b48" width="80%" height="70%"> <br/>
- PM10 평균 오차(RMSE) = 9.08
- PM2.5 평균 오차(RMSE) = 6.30
<br/>

### 3. 종로 3가 데이터 예측 결과
<img src="https://github.com/kyounggseo/perconal-projects/assets/102573192/a1655a22-5102-465c-b2ad-ce32f30290114" width="80%" height="70%"> <br/>
- PM10 평균 오차(RMSE) = 8.65
- PM2.5 평균 오차(RMSE) = 6.06
<br/>

### 4. 종로 4가 데이터 예측 결과
<img src="https://github.com/kyounggseo/perconal-projects/assets/102573192/b1b0b2b7-62b8-4ad5-9aab-d8fb14e0651e" width="80%" height="70%"> <br/>
- PM10 평균 오차(RMSE) = 11.10
- PM2.5 평균 오차(RMSE) = 8.56
<br/>

### 5. 종각역 데이터 예측 결과
<img src="https://github.com/kyounggseo/perconal-projects/assets/102573192/befe2f96-5f6f-4e51-a512-0a19cec1d56a" width="80%" height="70%"> <br/>
- PM10 평균 오차(RMSE) = 8.53
- PM2.5 평균 오차(RMSE) = 6.90
<br/>
  
### 6. 선정릉역 데이터 예측 결과
<img src="https://github.com/kyounggseo/perconal-projects/assets/102573192/a327c00e-713b-4336-b24e-5421818b2dfb" width="80%" height="70%"> <br/>
- PM10 평균 오차(RMSE) = 8.42
- PM2.5 평균 오차(RMSE) = 5.31
<br/>

## 3장. 분석 결과

#### 결과 및 평가
- 각 모델 학습 시간 : i7 CPU 기준 40분
- 실제보다 과하게 예측된 경향이 있음.
- 데이터 양 학습시간 대비 우수한 성능의 Model 도출

#### 한계점
- 겨울 데이터 확보시 모델에 계절적 주기성을 보완하여 좀 더 일반화된 모델을 만들 수 있음
<br/>

## 4장. 사업성 분석
- 시간단위 예측으로 Real-Time 의사결정 지원
  - 살수차 운용 등 정부 미세먼지 관리 대책 수립 및 이행에 시간 및 경제적 비용 감소
  - 요식업 등 미세먼지 영향을 받는 산업에 정보를 제공하여, 소비 패턴을 예상하고 대응을 가능하게 함
- 기존 미세먼지 예보는 필요한 데이터 종류/수가 많고 계산의 복잡성이 높은 단점이 있으나, 딥러닝 기반 예보를 활용하면 과거 미세먼지 데이터만을 가지고 저비용 고효율 시스템을 구축할 수 있다.
