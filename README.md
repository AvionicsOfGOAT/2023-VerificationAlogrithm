# 2023 GOAT [Verification of Algorithm]
This code repository is designed to demonstrate the Algoritm of <b>[Parachute deployment with Falling count]<b> and <b>[Z-score Outlier detection]<b>.

<br>

## Algorithm for Verification
### 1. Falling count alogorithm
- script name: F.C_parachute_deployment<br>
- purpose: 로켓의 최대 고도(Apogee) 도달 지점을 찾아 적절한 시간에 낙하산을 사출한다. <br>
- Algorithm logic: 적절한 윈도우 수를 찾아 moving average 를 사용하여 falling count를 세고, 사출한다.<br>
- Algorithm writers: 양태석, 박건우, 정재형, 이민형, 김윤수<br>

### 2. Z-score outlier detection algorithm
- script name: THRESHOLD_parachute_deployment<br>
- purpose: 1번 알고리즘의 정확도 향상을 위해, 이상치를 검출한다.<br>
- Algorithm logic: Z-score 공식을 사용하여 이상치를 검출한다.<br>
- Algorithm writers: 양태석, 박건우, 정재형, 이민형, 김윤수<br>

<br>

## SpaceX satellite dataset
https://github.com/r-spacex/SpaceX-API

### 1. CRS-8
![alt-text](https://github.com/AvionicsOfGOAT/2023_VerificationAlogrithm_ParachuteDeployment/blob/main/image/CRS-8.png)
### 2. CRS-12
![alt-text](https://github.com/AvionicsOfGOAT/2023_VerificationAlogrithm_ParachuteDeployment/blob/main/image/CRS-12.png)
### 3. Custom dataset
![alt-text](https://github.com/AvionicsOfGOAT/2023_VerificationAlogrithm_ParachuteDeployment/blob/main/image/customdata.png)

<br>

## Result
### 1. Falling count alogorithm

![alt-text](https://github.com/AvionicsOfGOAT/2023_VerificationAlogrithm_ParachuteDeployment/blob/main/image/falling_count.png)

CRS-12 데이터를 사용하여 최고 고도 도달 후, 사출까지 걸린 시간 A와, GOAT 로켓 스펙을 입력하여 openrocket에서 얻은 Apogee를 활용하여 계산
Falling count 13 으로 설정 시 예상되는 첫 번째 Deploy 시간은 9.501이다.

### 2. Z-score outlier detection algorithm

![alt-text](https://github.com/AvionicsOfGOAT/2023_VerificationAlogrithm_ParachuteDeployment/blob/main/image/z-score_threshold2.9_crs12.png)
![alt-text](https://github.com/AvionicsOfGOAT/2023_VerificationAlogrithm_ParachuteDeployment/blob/main/image/result2.9_crs12.png)

Z-core 계산 후 이상치 검출을 적용 시, threshold = 2.9는 이상치를 과도하게 잡고 threshold = 3는 이상치가 잡히지만 정확도가 떨어진다.
