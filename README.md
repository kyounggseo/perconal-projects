:book: 서울시 지하철 혼잡도 분석 프로젝트 <br/>

:round_pushpin: Subway Conjestion Analysis <br/>
서울시 지하철 혼잡도 분석

:round_pushpin: [개발 기간] <br/>
2022.04~2022.06

:round_pushpin: [프로젝트 개요] <br/>
아침 출근시간, 저녁 퇴근시간을 보면 유동인구가 많은 역에는 역무원들이 추가로 배치되어 있는 것을 볼 수 있다. 구토나 음식물로 인하여 전철이 오염되거나 갑작스러운 상황을 미리 대비하기 위해 적은 직원들을 효율적으로 배치하고 집중 분배를 시킬 필요가 있다. 집중분배를 하기 위해 승·하차 인원 정보 데이터를 이용하여 언제, 어디에 사람들이 제일 많이 모이는지 확인한다. 특히 2022년 코로나 거리두기 강화로 저녁 10시에 승·하차인원이 급증하게 되는데 이때 어느 지하철역의 사람이 제일 많이 모이는지 확인한다.
이 프로젝트를 통해서 서울 지하철의 직원을 효율적으로 배치하기 위해 서울시의 지하철 역 별 유동인구 분석, 지도 시각화 데이터 분석을 통하여 언제, 어디에 승객들이 가장 많이 모이는지 미리 예측할 수 있도록 도움을 주고자 한다. <br/>

:round_pushpin: [개발 언어] <br/>
Python 3.6.8

:round_pushpin: [IDE] <br/>
Jupyter notebook

:round_pushpin: [데이터 수집 및 전처리] <br/>
- 서울 열린 데이터 광장 - 서울시 지하철 호선별 역별 시간대별 승·하차 인원 정보<br/>
- 서울 공공데이터 API, 공공데이터포털 <br/>
<br/>
<br/>

:one: 데이터 전처리 - 지하철역 위치 <br/>
역 위치를 파악하여 지도를 통해 시각화를 하기 위해 folium라이브러리를 사용하였고, 지하철역 위경도를 뽑기 위해 googlemaps 라이브러리를 사용했다.  <br/>
ex) 
![image](https://github.com/kyounggseo/perconal-projects/assets/102573192/e73f481b-2d0a-4fae-b59a-de2ad2632ca6)  <br/>

:two: 데이터 전처리 - 시간에 따라 데이터 나누기 <br/>
<br/>
<br/>

:round_pushpin: result <br/>

:one: 서울시 지하철 호선별 역별 승하차 인원 정보 데이터<br/>
![image](https://user-images.githubusercontent.com/102573192/223920418-aa43ba47-c028-4fb2-ba04-3946c73a1592.png)<br/>

:two: 이용객이 많은 지하철 호선별 데이터 시각화<br/>
![image](https://user-images.githubusercontent.com/102573192/223919172-f25b36d1-46d9-41ba-9a1a-c323009da2d2.png)<br/>
이용객이 가장 많은 2호선 기준으로 승하차 인원 데이터를 추출하기<br/>
<br/>

:three: 2호선에서 역별 평균 승하차 인원 데이터 추출하기 => 평균 승하차 인원 수 내림차순으로 막대그래프 출력<br/>

- 승차<br/>
![image](https://user-images.githubusercontent.com/102573192/223920823-7ed1f037-7b8a-482f-b004-08cae458050b.png)<br/>
2호선 기준 3월 한 달간 강남 > 잠실 > 신림 > 구로디지털단지 > 홍대입구 > 선릉 순으로 평균 승차 인원이 많았다.<br/>
<br/>

- 승차를 가장 많이 한 곳<br/>
강남역 18시~19시 승차인원이 약 300만 명으로 제일 많았다.<br/>
![image](https://github.com/kyounggseo/perconal-projects/assets/102573192/cc9c8ddd-128a-467e-a550-f1f1c4b4e3f6)<br/>
<br/>

- 하차<br/>
![image](https://github.com/kyounggseo/perconal-projects/assets/102573192/412b8b88-509b-4cbc-84bc-b03de48abcdb)<br/>
평균 하차 인원은 거의 동일하게 강남 > 잠실 > 신림 > 구로디지털단지 > 홍대입구 > 역삼 순으로 많았다.<br/>
<br/>

- 하차를 가장 많이 한 곳 <br/>
가산디지털단지역에서 08~09시 하차인원이 약 350만 명으로 제일 많았다. <br/>
![image](https://github.com/kyounggseo/perconal-projects/assets/102573192/0c062270-0c4e-4f35-afc7-c415a8bfd44e) <br/>

참고로 이 값은 히트맵으로 본 시각화랑은 다르다.<br/>
(히트맵에서 강남역이 제일 많다고 생각하여 당연히 강남이라고 생각하면 안 된다.)<br/>
히트맵은 분포를 중심으로 보았기 때문에, 강남역 같은 경우 05시부터 23시까지 꾸준하게 많지만, <br/>
가산 디지털단지는 출근시간에만 하차하는 인원이 많고, 퇴근시간으로 갈수록 승차하는 인원이 증가한다. <br/>
많은 직장들이 모여있기 때문에 이러한 수치 값이 나온 것 같다. <br/>

:four: 특정 호선의 혼잡 정도를 지도에 출력<br/>
![image](https://user-images.githubusercontent.com/102573192/209819450-26b5c734-3dc3-4bc4-ba0b-ea2a29b33515.png)<br/>

:five: 연도별/시간대별 승객 
![image](https://user-images.githubusercontent.com/102573192/223921977-f35476c7-9c0b-434d-861b-956cdedcd657.png) <br/>
2020년도부터 출근시간대인 오전 6시~오전9시까지 2020년도 전과는 다르게 승객 수가 줄어든 것을 알 수 있다. 이는 2020년도에 확산된 코로나 19의 영향으로 재택근무의 비율이 많았다는 것을 알 수 있다. <br/>



