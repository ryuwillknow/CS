## BFS

그래프를 탐색하는 두 가지 방법

깊이 우선 탐색 : DFS

너비 우선 탐색 : BFS

주어진 상황을 정리하면 그래프이다. 이걸 잘 확인해야한다.

끝이 있다!!!!

앞사람에 대한 정보를 어떻게?

queue pop()을 가능한 부분을 바로 queue에 넣는다. 

탐색하는 과정의 순서를 바꾸는 법에 대해서

초기상태 - vis만들고 queue 생성하고 시작점 넣고 시작 ( 출발점이 여러개 있을 수도 있다. )

일단 queue에 넣고 방문 여부를 pop하고 확인한다!!!!!

전체까지 몇분 걸리나

최소까지 몇분 걸리나

누구에게서  ( 경로가 어려운거든 ) - 경로 어떻게 할 건데, 경로 어떻게 할건데

pop(0)를 조심

bfs는 재귀를 잘 쓰지 않는다.

bfs 2가지 visited 검증 처음 나중

```python
if __name__ == '__main__':
	print(main())
```
