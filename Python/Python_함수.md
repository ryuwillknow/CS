## ord

ord(’a’) = 97

ord(’z’) = 122

ord(’A’)=65

ord(’Z’)=90

## 함수

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
