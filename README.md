# 0. Intro
* **★공모전 설계서.pdf** 파일에 PT발표 자료가 있습니다. 먼저 보는 것을 추천 드립니다.
* 대회 : https://www.culture.go.kr/data/contest/main.do - 제 10회 문화데이터 경진대회 사이트

# 대회결과 
* 상장 이미지 추가

# 1. 파일설명
* 1. data preprocessing : 데이터 전처리 과정이 들어있는 폴더 입니다. 안에는 standard scale, log scale, UTMK 과정이 들어있습니다.
* 2. SPCA + Modeling : 차원축소 및 모델링 과정이 들어있는 폴더 입니다. 안에는 SPCA 과정 + Kmeans 와 Hierarchical의 비교가 들어있습니다.
* 3. 모델, 군집선정 + Pmedian : 모델을 통한 군집선정과 그 군집을 P-median 알고리즘을 통해 최적입지선정을 선택했습니다.

# 2. 진행방법

### 2-0 주제선정배경
* 주제 : 시니어 IT지원시설 최적입지선정
* 커져가는 시니어의 디지털 소외감에 대비해서 기존에 있는 주민센터와 복지관을 활용해서 시니어에 특화된 IT지원시설을 설치하면 좋겠다는 생각으로 주제를 선정하게 되었습니다.


### 2-1 데이터수집
* 문화 빅데이터 플랫폼 이외에도 마이홈포털, 서울복지포털, 서울열린데이터광장, LG유플러스, 한국문화정보원 등 여러 사이트를 통해 주민센터 및 노인복지관 데이터 및 여러 서울 데이터를 수집했습니다.

### 2-2 데이터 전처리
* 위치좌표 변환 및 데이터정규화 - 위, 경도를 UTMK좌표로 바꿔서 주민센터와 각 시설 거리간의 개수를 파악했습니다.
* Robust, MinMaxsclae, Standard Scale중 분류에 용이하고 특성들을 정규분포로 만드는 Standard Scale 을 채택했습니다.

### 2-3 차원축소
* SPCA 방법 이용 : 다변량 데이터에서 많이 쓰는 차원축소방법

### 2-4 모델선정
* K-means와 Hirarchical 중에서 전체 실루엣 계수와 각 군집별 실루엣 계수의 분산을 고려하여 균일하게 나누어진 K-means model(k=3)을 선정

### 2-5 군집채택
* K-means 군집별 변수 평균을 통해 상, 중, 하로 분류 한 다음 점수화
* 점수가 제일 높은 군집 중 가장 많이 등장하는 자치구 5곳을 선택

### 2-6 해당


