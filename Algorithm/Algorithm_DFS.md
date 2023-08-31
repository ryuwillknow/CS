## DFS 깊이 우선 탐색(빨리 다가보는 법)

비선형 구조를 빠짐없이 검색하는 방법 (DFS, BFS)

갈림길 정보를 stack에 저장한다. 내가 지나온 가장 가까운 갈림길에서 다시 탐색을 반복한다.

끝나면 뒷걸음질 친다.

처음 출발한 곳으로 오면 끝난다!!!

시작 정점 v를 결정하여 방문한다. 

나중에는 기본형 하나 만들 것이다. 

visited  + stack(간 길)

갈곳이 없는데 stack이 비어있지 않으면 pop

visited - 모두 true만들기

알파벳순으로 우선순위를 한다고 한다.

뒤돌아가면서 스택을 빼고 visited를 보면서 false인 곳으로 간다.

그래프라는 정보가 어떻게 주어지는이 보여줘야한다.

```python
```
7 8
1 2 1 3 2 4 2 5 4 6 5 6 6 7 3 7
'''
v, e = map(int, input().split())
arr = list(map(int, input().split()))
adjm = [[0] * (v + 1) for _ in range(v + 1)] #인접 행렬방식
adjl = [[] for _ in range(v + 1)) #인접 리스트 방식
for _ in range(e):
	v1, v2 = arr[i * 2], arr[i * 2 + 1]
	adjm[v1][v2] = 1
	adjm[v2][v1] = 1
	
	adjl[v1].append(v2)
	adjl[v2].append(v1)

adjm[v1] #v1과 연결된 모든 v들

```

```python
def depth_first_search(ver):
	visited[ver] = 1
	for nest in range(1, v + 1):
		if adjm[ver][next] == 1 and visited[next] ==0:
			depth_first_search(next) #연구하자
```

계산기, 백트래킹, 부분집합, 순열, 분할정복

문자열이 주어질 떄 스택을 활용하여 계산식의 값을 구할 수 있다.

계산기는 중위표기법, 후위표기법이 있다.  중위표기법을 후위표기법으로 바꾼후 스택을 활용해 계산한다.

연산자의 우선순위도 고려한다.

문자열에서 최소단위로 잘라낸 것이 토큰이다.

토큰이 연사면 스택 top과 비교, 높으면 push, 여는 괄호면push, 

## 백트래킹

**DFS는 노드간의 연결이 주어진다.**

**백트래킹은 2차원배열로 주어진다  - 이거 아님**

막히면 되돌아가서 다시 해를 찾아 가는 기법

백트래킹은 최적화문제와 결정문제(그런 경우가 있니 없니)를 해결할 수 있다.

ex 미로찾기, n-queen, map coloring, 부분집합의 합

1. 미로찾기

stack에 내가 어디로갔는지 남긴다. (좌표와 선택) + visited

없으면 pop

4방향 or 노드처럼 가능

DFS는 다 탐색한다.  만약에 여기에 if문이 있다면 백트래킹이된다.

prunning 가지치기다.! visited?? 안쓴다??? 

백트래킹 - 재귀를 활용한다…?

1. powerset  부분집합

후보군을 추천한다.

## 재귀와 dfs

```python
def dfs(now, vis)
	for next in range(100):
		if connection[now][next] == 1 and vis[next] == 0:
			dfs(next, vis)
```
