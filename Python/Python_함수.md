## 함수

함수의 기본 구조

```python
def function(data, key=None): # 함수의 input은 parameters이다.
	return #리턴이 없는 함수도 존재
```

return이 없는 함수는 Void function라고 한다. None을 반환하고 종료한다.

print와 return을 혼동하지 말자.

return 2개 하고 싶으면 튜플로 묶여서 나간다.

### Argument

---

Argument : 함수를 호출할 때 넣어주는 값

함수에서 Argument를 Parameter라는 변수에 넣어준다.

필수 Argument와 선택 Argument가 있다.

Positional Arguments - 함수 호출시 위치에 따라

Keyword Arguments - 직접 명시해주는 경우

**매우 중요**

```python
def add(x, y):
	return x + y

#이때 add(x=2, y=2), add(2,2), add(2,x=2) 가능하지만 add(x=2,0)은 안된다.
#positional argument가 먼저 나와야한다.
```

Default Arguments - 기본 값을 설정해준다.

```python
def add(x, y = 0):
	return x + y
```

Name space : 저장해두는 공간

1. built in - 파이썬 자체

1. global - 파이썬 실행 할 때

1. enclosing - 중첩시 밖의 name space

1. local - 함수를 실행할 때 함수 내부에 생성되는 

파이썬은 ‘LEGB’ 순서대로 찾는다. - 못찾으면 Error

파이썬의 SCOPE는 LEGB

**변수가 없는게 아니라 계속 찾는다는 뜻이다??**

- **함수로 print하고 나중에 print 하면 global이 없어서 오류가 나는 경우가 있다!!  not defined!!**

수명주기가 있다. B 는 파이썬이 실행되고 영원히. G는 파일, 모듈이 실행되고 끝날 때까지. L은 호출되면 생성되고 종료되면 끝

```python
a = 1  #이거 이거 매우 중요하다.
b = 2
def abc(c):
	return a + b + c
abc(1) == 4 #True

def abc(a,b,c):
	return a + b + c
abc(1) # Error
```

nonlocal(, global

```python
x =1
def func1():
	x=2
	def func2():
		x=3

```

## Rule

global을 여러곳에서 쓰면 정말 힘들어진다. - 알고리즘만 사용가능하다.

다 argument로 넘겨서 사용하자.

## ord

ord(’a’) = 97

ord(’z’) = 122

ord(’A’)=65

ord(’Z’)=90

## 추가

```python
def function():
    return 
```

## 판단 기준

리턴 값이 있다 없다. ()에 변수가 있다 없다.

## 지역변수, 전역변수

함수 내에 정의된 변수는 함수 내부에만 사용된다.

외부 변수를 가져오고 싶으면 global x를 선언해야한다.

## LAMBDA

```python
(lambda x : x+3)(3) #6
(lambda x,y : x+y)('abcd','1234')
```

활용

```python
list(map(lambda x,y : x+y,range(1,10))) 
#이건 안된다. y값이 마지막에 막힌다
list(map(lambda x : x+3,range(1,10)))
#이건 가능하다 
```

## Key가 있는 함수

max(iterable, key=)

딕셔너리, 튜플 in 리스트 일 때 첫번째 값을 가져온다.

Key에 함수를 넣는다.  lambda 가능하다

Key 있는 함수 목록 - 사실 나온다

.sort() max()

**키 있는 함수 만들기 - key는 반드시함수 특히 dict.get()**

```python
def ddd(a,key=None):
    if key == None:
        return a + 3
    else:
        return key(a) + 3
```

## Sorted()는 리스트를 내보낸다. replace도

## Eval(’문자열’) 은 문자열이 유요하다면 수식을 계산해준다.

## 재귀함수는 반드시 parameter가 필요. 다음항을 이야기할 수 있어야한다.

---

새로운 유형의 이야기. 일부로 함수 2개를 쓴거다.
