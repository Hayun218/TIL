## Spanning Tree
- 그래프 내의 모든 정점을 연결하는 트리 => 최소 연결 부분 그래프
	- => 트리의 형태을 자연스럽게 지니게 된다
	- => n개의 정점을 가진 그래프일 경우, (n-1)개의 최소 간선의 수
	
#### 특징
- DFS, BFS를 통해 찾을 수 O
- 모든 정점이 연결되어 있어야 하며, 사이클이 존재 하면 X 
- n개의 정점을 정확히 (n-1)개의 간선으로 연결!

![사진](https://gmlwjd9405.github.io/images/algorithm-mst/spanning-tree.png)

- Ex) 네트워크 구축

## Mininum Spanning Tree (MST)
- spanning tree 중 사용된 **간선의 가중치들의 합이 최소** 인 경우
- 특징은 spanning tree와 동일 
- e개의 정점을 지닌 간선의 갯수  = e*(e-1))/2

- Ex) 최소의 거리로 도로 건설, 최소의 비용으로 네트워크 구축

### 구현방법 

### 1.  Kruskal MST 알고리즘
- Greedy Method 
	- 결정할 때 그 순간에 가장 최적이라고 생각되는 방향으로 선택하여 최종 답안으로 가는 방식
	- 그 순간에는 최적이지만 전체 환경에서도 최적인지 고려해야 하는 방법
	- 크루스칼의 경우 이미 입증!!

- **유니온 파인드**자료구조를 기반! 
- 모든 간선에 대해서 가장 가중치가 적은 간선부터 연결하여 줌 => 간선선택 기반!

- 조건 
	- 1) 사이클이 생기면 안됨 => 사이클이 생긴다면 가장 작은 가중치를 지녔어도 무시	- 2) 모든 정점을 연결하여야 함 => 무조건 최소 간선을 선택
- 과정
1. 그래프의 간선들의 가중치를 오름차순으로 정렬
2. 정렬된 간선 리스트에서 사이클이 생기지 않는 경우로 최소 가중치를 선택하여 연결
3. 선택된 간선을 현재 MST 집합에 추가 

![과정](https://gmlwjd9405.github.io/images/algorithm-mst/kruskal-example2.png)

#### 사이클 생성여부 확인 방법
- 언제? 선택된 간선을 집합에 추가하고자 할 때 확인
- 추가하고자 하는 간선의 양 끝 정점이 같은 집합에 속해 있다면 => 사이클 형성 => 간선 무시하고 진행
- 이 때 유니온 파인드 사용!

#### 시간복잡도
- 정렬하는 방법으로시간 복잡도 결정!
- e개의 간선 퀵 소트와 같은 정렬할 경우
	- =>  O(ElogE)

### 2. Prim 알고리즘

