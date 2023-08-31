## Memoization

재귀호출이 비효율적이다.

재귀함수로 구현한 알고리즘은 문제가 있다. 중복호출이 존재하기때문이다.

피보나치 call tree를 봤을 때 i(1), i(2)를 여러번 호출한다.

```python
def i(n):
    if n == 1:
        return 0
    elif n == 2:
        return 1
    return i(n-1) + i(n-2)

for a in range(1, 20):
    print(i(a))
```

 복잡도가 2**n이다

memoization은 이전에 계산한 값을 메모리에 저장해 매번 다시 계산하지 않도록하여 실행속도를 빠르게 하는 기술이다. 복잡도를 n까지 줄인다.

```python
def fibo(n):
	global memo
	if n>= 2 and memo[n] == 0:
		memo[n] = fibo(n - 1) + fibo(n - 2)
	return memo[n]

memo = [0] * (n + 1)
memo[0] = 0
memo[1] = 1
```

하지만 함수호출이 있으므로 꽤 오랜시간이 소요됨은 피할 수 없다.

파이썬의 재귀함수 한계는 1000번이다.

## DP Dynamic Programming 동적 계획법  D&C(divide and conquer)

반복구조 느낌?

계산했던 것을 저장해둬서 불러오기

최적화 문제를 해결하는 알고리즘

부분문제의 답을 통해 본문제를 해결한다.

```python
def fibo2(n):
	f = [0] * (n + 1)
	f[0] = 0
	f[1] = 1
	for i in range(2, n+1):
		f[i] = f[i - 1] + f[i - 2]

	return f[n]
```

매우 간단해졌다.  재귀냐 DP냐 잘 생각해봐야한다.

```python
#while 사용 가능
def fibo_while(n):
	a, b = 0, 1
	count = 0
	while count < n 
		a, b = b , a + b
		count += 1
	return a
```
