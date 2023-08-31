## 2차원 배열

```python
'''
3
123
456
789
'''
N = int(input())
arr = [list(map(int, input())) for _ in range(N)]

#1차원은 가능하다.
a = [0] * N

'''

'''
#2차원은 안된다.
a = [[0] * 3] * 3 #절대 안됨
a = [[0] * 3 for _ in range(3)] #으로 해야한다.
```

배열 접근

```python
#행 우선 순회
for i in range(n):
	for j in range(m):
		arr[i][j]
#열 우선 순회
for j in range(m):
	for i in range(n):
		arr[i][j]
#지그재그 순회
for i in range(n):
	for j in range(m):
		arr[i][j + (m - 1 - 2 * j) * (i % 2)]
```

델타 제일 중요하다. - 주변 ㅋㅋㅋ

```python
#조심해야할 점 : 더하면 밑으로 내려간다.!!!! + 가장자리 확인

di = [0, 0, 1, -1]
dj = [1, -1, 0 ,0]

for i in range(n):
	for j in range(m):
		for k in range(4):
			ni, nj = i+di[k], j+dj[k]
			if 0<=ni<N and 0<=nj<N: #넘어가지 않는 것들만
				print(i, j, ni, nj)

#점점 커져갈 때 누적해서 더하는 것
#for문 하나 더 나오고 l변수를 통해 dj, di 에 l을 곱해준다.

#전치행렬
for i in range(3):
	for j in range(3):
		if i < j: #대각선 반띵 
```

## 부분집합합

모든 부분집합을 다 확인한다. - 완전검색 기법 - 가장 기본적이다.

N개의 원소를 갖는 집합은 2**N의 경우의 수를 갖는다.

bit으로 만든다. 포함이거나 아니거나 

나는 공집합 포함으로 생각했는데 아닐 것이다. 집합이맞다. 

```python
A = (1,2,3,4)
bit = [0, 0, 0, 0]
for i in range(2):
	bit[0] = i
	for j in range(2):
		bit[1] = j
		for k in range(2):
			bit[2] = k
			for l in range(2):
				bit[3] = l
				print(bit, end = ' ')
				for m in range(4):
					if bit[m]:
						print(A[m], end = ' ')
				print()
```

나중에는 재귀로 한다!!!!!

## 비트연산자

8bit = 1byte

메모리의 주소는 byte 단위로

1 << n  이건 2의 n제곱이군 (n번 비트가 1인 값을)

i & (1<<j)   j번 비트가 1인지 아닌지 검사한다.

비트로 인식하게 하는 조건
