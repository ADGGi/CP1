# 악플분류+비속어탐지 프로젝트


프로젝트 과정
-------------------
1. 데이터 수집
    - 데이터 수집 기간 : 2021/12/13~2021/12/14
    - YouTube 인기동영상 댓글 26836개
    - DC Inside 게시글 22883개
    
2. 전처리 
    - 한글, 영어, 일부 특수문자를 제외하고 제거
    - 'ㅋㅋㅋㅋ', 'ㅠㅠㅠㅠ' 등 연속적으로 반복되는 글자는 2글자로 단축
    - 2칸 이상의 공백은 1칸으로 단축
    - 문장의 맨 앞과 맨 뒤의 공백은 제거
    - 라벨링 기준 설정
        - 욕설과 비속어의 사용은 악성댓글(1)로 라벨링
        - 합리적 이유없이 성별, 종교, 장애, 나이 등을 차별하거나 이에 대한 편견을 조장하는 내용은 악성댓글(1)로 라벨링
        - 욕설, 비속어의 사용 없이 표현이 가능하지만 비난, 비방을 목적으로 과격한 단어가 들어간 내용은 악성댓글(1)로 라벨링

3. 모델 성능 비교
    - 각 모델마다 3-Fold cross validation
    
|Models|	ROC AUC Score|
|-------|--------|
LGBM|	0.695|
Bi-LSTM|	0.881|
1D-CNN|	0.911|


4. 최종 모델 선정

<img src="https://user-images.githubusercontent.com/86307300/151268099-51db2ffe-3467-4c28-95bd-d5994ccf12e7.png"  width="300">

향후 프로젝트 진행 목표
----------------------
1. BERT 모델과 성능 비교
2. 악플로 분류된 문장에서 가장 높은 영향을 준 단어에 마스킹하는 알고리즘 적용
