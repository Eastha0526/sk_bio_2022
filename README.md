# AI Challenge for Biodiversity 

  - https://dt-training.center/contests/summaries/view?contestId=11
  
## 대회 개요

  - 지속되는 환경오염과 기후변화로 인하여 자연 생태계가 파괴되고 지속가능한 발전 필요
  - 생물다양성을 증대시키는 방법 필요
  - 데이터 분석을 통하여 그러한 방법을 모색
  ![image](https://user-images.githubusercontent.com/110336043/219582393-ab4e07b4-e70e-40e7-af91-8a6b4a5cf75b.png)
  
  ![image](https://user-images.githubusercontent.com/110336043/219582757-8fccafde-de7e-416a-af29-c8e591991c25.png)

  - 여러 데이터 분석 방법 중 Predictive및 Prescriptive 분석 방법을 활용

## 대회 기간
  
  - 2022.10.05-10.31
  
## 데이터 분석 방법

  - http://kienews.com/news/newsview.php?ncode=1065597829283508
  - 위의 기사를 통하여 30년간 국내 기후변화가 생물다양성에 영향을 끼친것으로 확인
  - 그다음, 레이블이 없는 1990년부터 2017년 사이의 데이터는 Semi-supervised Learning 중하나인 LabelSpreading을 사용하여 레이블이 있는 데이터로부터 예측 및 생성하여 레이블을 부여했다.
  - 그 후 Binary Classification 모델을 생성하여 앞서 언급한 생물다양성이 보장되는 기후가 되는 그 분기점을 예측하여 찾았다.
    - RandomForest와 간단한 MLP모델을 통하여 두가지 모델을 비교하여 더 성능이 좋은 모델 확인
      - RandomForest의 경우 feature importance를 통하여 어떠한 feature가 기후에 영향을 크게 미치는 지 확인
      - MLP의 경우 일반화된 모델을 통하여 더 많은 곳에서 시민 데이터 과학자들 및 일반 사용자들에게도 사용할 수 있기 위하여 모델 제작

## 사용 데이터

  - 활용한 외부 데이터
       - 조류분포, 등장 시기, 개체 수 데이터
       - 한국과학기술정보연구원_국내 조류분포 ('93~'00)
          - https://www.data.go.kr/data/3033734/fileData.do
       - 국립생태원_제4차 전국자연환경조사 조류 조사보고서 ('14~'18)
          - https://www.data.go.kr/data/15106213/fileData.do
       - 기온, 자외선, 풍속, 오존, 이산화황, 일산화탄소, 강수량, 이산화탄소 데이터
       - 기상청 기상정보개방포털
          - https://data.kma.go.kr/cmmn/main.do
       - 발전 방법별 발전량 데이터
       - 한국전력 KEPCO 전력통계월보
          - https://home.kepco.co.kr/kepco/KO/ntcob/ntcobView.do?pageIndex=1&boardSeq=21059203&boardCd=BRD_000097
          
          
## FeedBack
  
  - 점수
    - ![image](https://user-images.githubusercontent.com/110336043/219584966-18c5bfff-009d-4f43-b247-163559a9680f.png)

  - 외부 데이터를 활용하였지만 그 활용하는 데이터가 활용하기 모호한 부분이 있었고 부정확한 데이터를 사용하였다.
  - Semi-supervised learning을 이용해 데이터 label의 문제를 해결함으로써 단기적 feature 분기점이 아닌, 장기적으로 이상적인 기후 환경을 예측함으로써 매우 설득력 있는 분석을 진행한 것으로 판단됨
  - 또한 오버샘플링 기법 중 SMOTE를 활용하여 데이터 imbalancing을 줄일려고 하였음
  - 하지만 제공 데이터는 사용하지 않은 점, 외부 데이터가 부정확한 점에서 감점
  - 또한 기사 하나만 근거로 제시하여 실질적으로 근거가 되기에 부족하다.

## 개선사항

  - 위와 같은 평가를 기반으로 하여 추가적으로 조금 더 이 분석이 과학적 및 환경적으로 적합한지 추가적인 근거 필요
  - 데이터 개선 필요
    - 단순히 기상청에서의 데이터와 연간 에너지 이용량 이외에 더 충족할만한 데이터 추가 필요
    - 또한 hyperparameter tunning시 vaildation을 통하여 개선하지 않은 점 수정 필요
    - 앞으로의 미래 예측시 단순한 데이터 예측 말고 RNN 및 시계열 분석을 통하여 좀 더 설득력 있는 예측데이터를 통하여 향후 개선사항을 하였으면 더 좋은 분석이였을 것 같다.
