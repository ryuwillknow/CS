## 순차

일렬로 되어 있는 자료를 순서대로 검색하는 법

알고리즘이 단순하여 구현하기 쉽지만 

상황 2가지가 있다 - 정렬되어있는 경우, 정렬되어있지 않은 경우

1. 정렬되지 않은 경우

첫번째 원소부터 순서대로 찾는다.

키값이 동일한 원소를 찾으면 인덱스 반환. 없으면 실패 ( 다음이 없는데? )

시간 복잡도 O(n)

```python
def search(a, n, key):
	i = 0
	while i < n and a[i] != key :
		i += 1
	if i == key : 
		return i
	else:
		return -1
```

for, while 큰 차이 없다.

1. 정렬된 경우

내가 원하는 값보다 크면 멈춘다. 끝까지 안간다

```python
def search(a, n, key):
	i = 0
	while i < n and a[i] < key :
		i +=1
	if i < n and a[i] == key:
		return i
	else:
		return -1
```

평균적으로 횟수가 반으로 줄어든다.

for문을 쓰면 break를 해줘야한다…? 다양하다!

## 이진 검색

절반을 찍고 다시 절반을 찍는다. 

조건 - 자료가 정렬된 상태여야한다!!!

목표값이 중앙값보다 크면  오른쪽 작으면 왼쪽 - 찾을 때까지 반복하면 된다.

구간의 L 과 R  C값

key가 c보다 크다면 L 이 C+1이 된다. 이런식

이러다가 구간이 뒤집어진다면 검색실패한다

리스트가 삽입, 삭제가 발생했을 때 정렬을 유지하기 위해 추가 작업이 필요하다.

```python
def binarysearch(a, n, key)
	start = 0
	end = n - 1
	while start <= end:
		middle = (start + end) // 2
		if a[middle] == key:
			return True
		elif a[middle] > key:
			end = middle - 1
		else :
			start = middle + 1
	return False
			
```

개념 재밌다!!! - 이정도는 해야한다. 글 그림으로 하고 나중에 해야한다. 

재귀로 할 수 있지만 반복이 더 빠르다

## 인덱스

테이블에 대한 동작속도를 높여주는 자료구조를 일컫는다

## 선택정렬

거품정렬, 선택정렬 다 잘해야한다.

주어진 리스트에서 최소값을 찾는다.

리스트의 맨 앞에 위치한 값과 교환한다.

반복한다.

O(n**2)

```python
def selectionsort(a, n):
	for i in range(n-1):
		mini = i
		for j in range(i, n):
			if mini > a[j]:
				mini = j
		a[i], a[mini] = a[mini], a[i]
		
```

비교연산이 많이 든다.

## 셀렉션 알고리즘

최대값 최소값 중간값을 찾는 알고리즘

정렬하고 원하는 순서에 원소 가져오기

## 중간 정리

효율은 카운팅정렬이 가장좋다… 

단 선택정렬은 교환횟수가 적다

## 리스트 복사하는 법

for 문안에 a[i][j]를 사용해서

a[i][j]는 리스트가 아니다. 이건 하나의 값이므로 리스트처럼 따라가지 않는다.
