# BigContest_ECOtamra
2021 BigContest 퓨처스리그 ECO제주, 에코탐라

## 개요
* 주제 : 제주도 음식물 쓰레기양 예측을 통한 배출량 감소 방안 도출
* 기간 : 2021.07. ~ 2021.09.
* 팀원 : 김서린, 김소은, 신정아, 이윤지
* 사용언어 : Python

## 분석내용  
1. 데이터 전처리
* target : waste_amt(음식물 쓰레기 배출량)
* 설명변수 : koraen(내국인 유동인구), long_term_frgn(장기체류 외국인 유동인구), short_term_frgn(단기체류 외국인 유동인구), resident(총 거주인구), card_cnt(음식관련 카드 결제건수), card_amt(음식관련 카드 결제금액), waste_cnt(음식물 쓰레기 배출건수), detached(단독주택), apt(아파트), town(연립주택), multiplex(다세대주택), commercial_building(비거주용 건물 내 주택), distancing(사회적 거리두기 단계), temp(월평균기온), rain(월 강수량)
2. 변수선택
* 상관분석, 회귀분석 이용하여 변수 선택
3. XGBoost
* 변수들을 조합하며 RMSLE 비교하여 최적의 모델을 선정  
* 최종 모델
- korean, long_term_frgn, short_term_frgn, resident, card_cnt, card_amt, waste_cnt, detached, apt, town, multiplex, commercial_building, distancing
4. ARIMA model
* 각 변수의 2021년 7, 8월 값 예측
![image](https://user-images.githubusercontent.com/86909645/167281419-80d6f903-4a4a-4ded-8cae-10c4ead31012.png)
5. 예측 결과
* train data : 2018.01. ~ 2021.06.
![image](https://user-images.githubusercontent.com/86909645/167281441-41394ecb-bc9e-4c2b-afbd-f7021b5ae744.png)
* 2021.07. 예측 결과
![image](https://user-images.githubusercontent.com/86909645/167281449-8cfe6003-bcbd-4948-bf89-bbf45530f537.png)
* 노형동, 연동, 이도2동 등 제주도 시가지 지역을 중심으로 배출량이 많을 것으로 예측
* 2021.08. 예측 결과
![image](https://user-images.githubusercontent.com/86909645/167281476-79729595-df23-4201-9a46-f368b573f0bc.png)
* 7월 배출량에 비해 전체적으로 배출량이 증가할 것으로 예측
* 지역은 7월과 유사

## 결론
![image](https://user-images.githubusercontent.com/86909645/167281509-953bbd9f-0fbb-4c8b-a97f-bc79ceb6d13f.png)

