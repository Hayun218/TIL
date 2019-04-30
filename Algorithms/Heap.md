## Heap

``` 스스로 요약

```
#### 종류
 - 최대 힙 : 부모노드의 값이 더 큰 경우
 - 최소 힙 : 부모노드의 값이 자식노드보다 더 작을 경우

#### 특징
- 완전 이진 트리의 일종
- 여러 개의 값들 중에서 최댓값이나 최솟값을 빠르게 찾아내도록 만들어진 자료구조
- 우선순위 큐(주로 사용됨! O(logN), 힙 정렬O(NlogN)
- 중복된 값 허용
- 배열로 구현

#### 효율성
![시간복잡도](https://gmlwjd9405.github.io/images/data-structure-heap/data-structure-heap-priorityqueue.png)

#### 힙에서의 부모 노드와 자식 노드의 관계
- 배열에서 1부터 시작! => 0 부터 시작도 가능하지만 편의를 위해 => 0부터 할 경우 밑에 왼쪽 오른쪽 자식의 ㄴ인덱스에 +1씩 
- 왼쪽 자식의 인덱스 = (부모의 인덱스) * 2
- 오른쪽 자식의 인덱스 = (부모의 인덱스) * 2 + 1
- 부모의 인덱스 = (자식의 인덱스) / 2
	
![관계](https://gmlwjd9405.github.io/images/data-structure-heap/heap-index-parent-child.png)

#### 삽입
- 다른 노드는 바뀌지 않고 마지막 노드에 새로운 요소를 추가 
- 최대 힙 혹은 최소 힙 의 특징에 맞추어 새로운 노드를 부모노드와 비교하여 rearrange

* 최대 힙
![힙에서 서로 교환](https://gmlwjd9405.github.io/images/data-structure-heap/maxheap-insertion.png)

#### 삭제
1. 최대 힙에서 최댓값이 루트노드이며 루트노드를 먼저 삭제
	- 최대 힙에서 최대값을 먼저 삭제시켜야 함 (최소 힙에서는 최소값부터)
	
2. 삭제된 루트노드에는 마지막 노드 값을 가지고 옴
3. 다시 재정비

* 최대 힙
![최대힙 삭제](https://gmlwjd9405.github.io/images/data-structure-heap/maxheap-delete.png)


[참고자료] <https://gmlwjd9405.github.io/2018/05/10/data-structure-heap.html>