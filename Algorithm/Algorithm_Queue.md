# Queue

선입 선출 구조 FIFO     (vs  LIFO)

queue는 먼저 들어온 위치와 마지막에 들어온 위치 2개를 관리한다.

front(먼저 들어온)  rear

stack의 push 와 pop과 같이

queue는 enqueue와 dequeue가 있다.

queue는 다양한 방법이 있지만 이번에는 이 방식으로

처음에 front = rear = -1

front만 상승한다. 

front와 rear가 같으면 비어있다.

## 선형 큐

큐 크기 = 배열의 크기

front =  마지막으로 삭제된 원소의 index

rear = 마지막으로 저장된 인덱스

상태표현

front = rear = -1  : 초기상태

front = rear  : 공백상태

rear == n - 1  : 포화상태

que.append(a)

que.pop(0)

매우 느려질 가능성이 있다.

덩치가 크면 정석대로 해야한다. 

from collection import deque

q1 = deque

q1.popleft()   정석만큼 빠르다.

원형큐

가득차지 않았다는 조건에서 받는다.  

% len(q) 라는 개념을 활용한다.

우선순위 큐도 있다.
