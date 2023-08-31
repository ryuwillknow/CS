## 자료구조와 알고리즘

https://wikidocs.net/189480 → 파이썬은 모든 것이 변수이다.

배열 - 다른 언어는 배열 안에 값이 그대로 있다 + 연속한 메모리에 저장한다.

파이썬은 객체 주소를 전달하기 때문에 자유도가 높다. 크기와 내용물을 변경하기 쉽다. 동적배열. 정적 배열은 

https://hkim-data.tistory.com/182

### 상호 배타적 집합 (Union Find 알고리즘)

중복된 원소가 없는 집합을 의미한다.  그래프 알고리즘이다!! MST에 사용?

rank도 필요하다. 원리를 잘 생각해보자.

```python
# 집합 생성
parent = [i for i in range(V)]  

# x를 포함하는 집합 찾기

# union(x, y) x안에 y를 넣는다.

```

### 연결리스트 in python

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

head = Node(1)
head.next = Node(2)
head.next.next = Node(3)

# 뒤에 추가하기
node = head
while node.next:
    node = node.next
node.next = Node(4)

# 처음에 추가하기
node = Node(0)
node.next = head
head = node

node = head
while node:
    print(node.data)
    node = node.next
```

프로그래머스의 표편집 문제, Linkedlist 라는 것을 만들자!!!! head == current

root 라는 개념!!

순환 찾기

```python
def is_there_loop(_list):
    node1 = node2 = _list.head
    while node1 and node1.next:
        node1 = node1.next.next #첫째 노드는 두 칸씩 이동
        node2 = node2.next      #둘째 노드는 한 칸씩 이동  순환이면 언젠가는 만난다.
        if node1 == node2:
            return True
    return False
```

연결리스트 뒤집기

```python
class Linked_list:

    def reverse(self):
        if self.length <= 1:
            return
        ahead = self.head.next
        prev = self.head
        prev.next = None
        while ahead:
            self.head = ahead
            ahead = ahead.next
            self.head.next = prev
            prev = self.head
```

### 해시테이블 = 딕셔너리 해시맵

해싱 ⇒ 문자열을 함수로 바꾼다. 리스트에 맞게 넣는다.

기본 hash() 함수가 있다.

### 트리 (계층으로 구성되고 순회가 없는 그래프 = 인접 리스트, 인접 행렬로 구현가능)

이진트리는 리스트로 구현가능 

//2 하면 부모 곱하기 2 , 곱하기 2 + 1하면 자식

재귀로 순회할 수 있다.  스택으로 순회할 수 잇다.

### 힙

완전이진트리라 배열로 구현한다

heapq 사용하자!!

우선순위 큐를 구현하기 위한 자료구조이다. 들어온 순서와 관계없이 우선순위에 따라서 나간다.

최소힙은 부모가 자식보다 작거나 같은 트리. 파이썬의 heapq는 최소 힙니다.

왼쪽부터 채워야한다.

heappush, heappop

```python
# heappush는 가장 끝에 넣고 그 다음에 바꾼다.

def heappush(heap, data):
    heap.append(data)
    # 추가한 원소의 인덱스를 구한다.
    current = len(heap) - 1 # current는 지금 넣은 원소
    # 현재 원소가 루트(인덱스 0)에 도달하면 종료 이부분이 중요하다!
    while current > 0:
        # 추가한 원소의 부모 인덱스를 구한다.
        parent = (current - 1) // 2
        if heap[parent] > heap[current]:
            heap[parent], heap[current] = heap[current], heap[parent]
            # 추가한 원소의 인덱스를 갱신한다.
            current = parent
        else:
            break

# heappop  마지막이랑 처음거 바꾸고 pop 양쪽 노드중에 작은거 바꾼다. 만약 없거나 둘다 크면 멈춤 

```

heapify ( 배열을 힙으로 만들기 ) 이게 제일 어렵다??

하나의 객체로 소통한다. 이거가 주된 논리?

### 이진 검색 트리

이친구가 레전드 연결리스트로만? + 왼쪽 오른쪽.

### 인접 리스트와 인접 행렬

https://duwjdtn11.tistory.com/515   + 가중치 구현은 튜플을 append하는 것으로?

그래프를 표현하는 두가지 방법이다.

트리와 그래프의 차이

https://bigsong.tistory.com/33

트리는 사이클을 허용하지 않는다.

레벨이 존재한다. root 존재한다.

노드 N개에 간선 N-1개
