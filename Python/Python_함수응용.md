# 내장함수

---

1. map()  {range,  dict_keys, dict_values 와 같고  replace와 다른}

1. filter() : True만 나온다.

```python
def odd(n):
	return n%2
numbers = [1,2,3]
result = filter(odd, numbers)
print(result, type(result)) # 이건 오브젝트로 나온다.
print(list(result)) # [1,3]
```

1. zip(*iterables)  

```python
girls = ['jane', 'ashley']
boys = ['justin', 'eric']
pair = zip(girls, boys)
print(pair, type(pair))
print(list(pair))
```

1. lambda [   ]  : 익명함수

```python
(lambda a : a + 2)(2) #4
```

# 재귀함수

---

자기 자신을 호출하는 함수

예시

```python
def recur():
	print('뿅')
	recur()

#무한히 반복한다. recursion error 발생한다.
```

팩토리얼(!)을 쓸 때 사용된다? n! = n * (n-1)!

```python
def fac(n):
	if n == 0:
		return 1 #break 안된다. break는 while, for 만 사용한다.
	return n * fac(n-1)
```

재귀함수는 base case를 반드시 넣어야한다. base case는 언제 끝나는지.

머리속에 그리기가 힘들다. → 그림을 그려보세요.

재귀함수 계산 순서 - 모든 함수가 계층적으로 들어가면서 계속 진행되고 base case에서 계산되면서 역순으로 계산된다. (다시 돌아온다.)

# 패킹 언패킹

---

print() 는 신기하게 argument 개수가 제한이 없다.

```python
z = 1, 2, 3 #튜플된다.
a, b = 1, 2, 3 #ValueError : too many values to unpack
```

## 패킹

*는 남는거 다 넣어서 리스트를 만들어라. 

## 언패킹

*는 다 풀어라

## 함수에 패킹, 언패킹 활용 (가변인자)

```python
def test(*values):
	for value in values:
		print(value)  # 가변인자가 된다.
test(1,2,3,4,5,6)
test(2,1,23,3) # 다 가능하다.
test([1,2,3,4]) # print하면 [1,2,3,4]가 된다.
```

## 키워드 가변인자 - **는 Dict으로 전해준다. (Asterisk 2개)

```python
def test(**keyword_argument):
	return keyword_argument
test(name = 'aiden', age = 12)

#키워드와 키워드가 아닌 것
def test(*args, **keyword_argument):
	return keyword_argument
test(1,2,3,4,name = 'aiden', age = 12)

#응용 : 처음과 마지막은 고정
def test(a, *args, **keyword_argument,e):
	return keyword_argument
```

# 모듈

---

.py 파일 하나를 말한다. 

함수를 모아서 .py를 모듈

모듈을 모아서 폴더를 만든 것이 패키지

패키지를 여러개 묶어 놓은 것을 라이브러리

**함수 - 모듈(.py) - 패키지(폴더) - 라이브러리(폴더)**

패키지 , 라이브러리가 모호하게 사용된다.

## pip 라이브러리 관리자

---

전세계 모듈을 가져올 수 잇다.

파이썬 설치시 자동으로 

PyPI에 자동 접근

bash, 터미널에서 pip install SomePackage==1.0.5 

버전명, 최소버전

다른 컴퓨터에 전송하려면 내 패키지 목록을 보내서 상대가 설치해야한다.

- 패키지 관리하기

pip freeze > requirements.txt

pip install -r requirements.txt

## 패키지 활용공간 (가상환경)

---

## 사용법

---

```python
import module
from module import var, funcion, Class
from module import * # 모든 것을 가져와

from package import module
from package.module import var, funcion, Class
```

모두 불러오면 파일이 커진다.

## 패키지 만들기

---

```python
#폴더 안에 __init__.py 생성하기 - 폴더를 패키지로 인식한다.

#모듈 안에 두개 함수있다면
tool.add(1,2)
tool.sub(1,2)

from calc.tools import add, sub
add(1,2)
sub(1,2)

# 무조건 짧다고 좋은게 아니다. 코드가 길어지면 정확하게 보여줘야하므로 모듈 하나 가져오는 것을 추천한다.
```
