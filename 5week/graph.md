## 그래프
- 그래프의 `지름(Diameter)`은  정점 간 거리의 `최댓값`
- `연결성(Degree)`은  그 정점과 `연결된 간선의 수` ex d(v)  방향성 그래프에는 in과 out이 있음.

### 랜덤 그래프 프 𝐺(𝑛, 𝑝)
- 에르되스-레니 랜덤 그래프(Erdős-Rényi Random Graph)
- 𝑛개의 정점을 가집니다
- 임의의 두 개의 정점 사이에 간선이 존재할 확률은 𝑝입니다
- 정점 간의 연결은 서로 독립적(Independent)입니다

- 에르되스-레니 랜덤 그래프의 확률
<img src=image/erdos.PNG>

## 작은 세상 효과
- 임의의 두 사람을 골랐을 때, 몇 단계의 지인을 거쳐 연결되어 있을까?
- 25%의 편지만 도착했지만, 평균적으로 6 단계만을 거쳤습니다.
- 한국에서는 “사돈의 팔촌”이 먼 관계를 나타내는 표현으로 사용됩니다
- 즉, 아무리 먼 관계도 결국은 사돈의 팔촌(10촌 관계)입니다
- 높은 확률로 랜덤 그래프에도 존재
<img src=image/smallworld.png height=500 width=500>
 
#### *작은 세상 그래프는 균일 그래프의 일부 간선을 임의로 선택한 간선으로 대체한 그래프
 
### 체인(Chain), 사이클(Cycle), 격자(Grid) 그래프에서는 작은 세상 효과가 존재하지 않음
<img src=image/nosmall.PNG>

### 두터운 꼬리 분포
- 실제 그래프에서는 연결성이 매우 높은 허브(Hub) 정점이 존재함
- 랜덤 그래프는  높은 확률로 정규 분포기 때문에 허브(Hub) 정점이 존재할 가능성은 희박.

## 거대 연결 요소

### 연결 요소(Connected Component)
- (1) : 연결 요소에 속하는 정점들은 경로로 연결될 수 있습니다
- (2) : (1)의 조건을 만족하면서 정점을 추가할 수 없습니다
- 노드가 모두 이어져있는 부분 집합 그래프라고 생각하면 될듯

- 실제 그래프에는 거대 연결 요소(Giant Connected Component)가 존재합니다
- 거대 연결 요소는 대다수의 정점을 포함합니다.
<img src=image/big.PNG>
 
### 랜덤 그래프에도 높은 확률로 거대 연결 요소(Giant Connected Component)가 존재 
- 단, 정점들의 평균 연결성이 1보다 충분히 커야 함  (feat. Random Graph Theory )
<img src=image/randbig.PNG>

## 군집 구조 - Community

### 지역적 군집 계수(Local Clustering Coefficient)
- 한 정점에서 군집의 형성 정도
- 정점 𝑖의 지역적 군집 계수는 정점 𝑖의 이웃 쌍 중 간선으로 직접 연결된 것의 비율
<img src=image/comm.PNG>
 
- C1 = 노드1 제외하고 -> 연결된 간선 수 / 있을 수 있는 간선 경우의 수 
- 참고로 연결성이 0인 정점에서는 지역적 군집 계수가 정의되지 않음.
#### 정점의 지역적 군집 계수가 매우 높으면, 이웃 노드는 높은 확률로 간선이 있다. -> 높은 확률로 군집을 형성

### 전역 군집 계수(Global Clustering Coefficient)
- 전체 그래프에서 군집의 형성 정도
- 전역 군집 계수는 각 정점에서의 지역적 군집 계수의 `평균`

#### 실제 그래프에서는 군집 계수가 높습니다. 즉 많은 군집이 존재합니다 -> 유사한 것끼리 연결 가능성이 높음.
#### 반면 랜덤 그래프에서는 지역적 혹은 전역 군집 계수가 높지 않습니다. -> 간선 연결이 독립임.