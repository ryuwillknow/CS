## Heap : 완전이진트리여야한다.

완전이진트리 에 있는 노드중 키값이가장 큰 노드나 키값이 가장 작은 노드를 찾기 위해 만든 자료구조

최대 힙은 부모가 항상크다. 최소힙은 부모가 항상작다. 루트가 가장 크거나 작다.

이걸 우선순위 queue를 구현하는데 사용한다.

삽입한후 변화를 시킨다. 이게 중요하다!!!

```python
while parent != 0 or parent > cur
	cur, parent = parent, cur

# parent = cur//2
```

힙은 루트의 원소만을 삭제할 수 잇다.

마지막 부분을 루트에 넣는다. 

더 큰 쪽과 비교하면서 바꾼다.

append pop하지 말고 size를 정해서 heap을 만들자

```python
# 대부분 반복이다. 재귀가 많이 안쓴다..? 순회만 재귀다?

heap = [0] * 101
last = 0 #이게 중요하다  -1이 아니다.

cur = last
parent = c // 2

while parent != 0 or parent > cur
	cur, parent = parent, cur
```

```python
def enq(n):
	global last
	last += 1
	heap[last] = n
	c = last
	p = c//2
	while p > 0 and heap[p] < heap[c]:
		heap[c], heap[p] = heap[c], heap[p]
		c = p
		p = c//2
	return
```

여기가 헷갈린다.

```python
def deq():
	global last
	temp = heap[1]
	last -= 1
	heap[1] = heap[last]
```
