# 디버깅

---

버그를 잡기

문법에러와 로직에러 두 개가 있다.

문법에러 (Syntax Error)

예외처리(exeption) : 에러를 예외처리로 제어한다.

**예외 계층구조가 있다.** 부모를 만나면 자식을 만나면 이런 경우를 따져야한다. 

가장 작은 에러부터 처리하는 코드를 써야한다. 

런타임 error 가 문법이 올바르더라도 발생하는 에러

기대했던 값이 아닐 때?

NameError : 변수 없다.

TypeError : 클래스가 맞지 않다. 인자가 부족하던가 넘칠때도

ValueError : 값에 문제가 있다. 

IndexError : 아이템이 부족하거나 그 위치에 없을 때 리스트에서?

KeyError : 딕셔너리, get을 사용하면 안생긴다.

KeyboardInterrupt : ctrl c

```python
try:
# 예외 발생하면 except실행
except ValueError as err:
	print(f'{err}, 오류가 발생했습니다.')

except (ValueError, ZeroDevisionError): #이것도 가능하다.

else: #try에 문제가 없다면 실행함. like for break else문과 같다.
	print('something')

finally:
# 무조건 실행
```

try는 except가 필요하다.

아하 ctrl + c를 누르면 except가 뜬다

except에 없으면 에러가 뜬다.  except에 예외가 없으면 나머지 모두가 적용된다. 

raise → 특정조건에서 에러를 일으키자!

```python
raise ValueError('나는 에러지롱') 
```

assert →  특정 상황에서 예외 발생시킬 때, 디버깅용도로 사용한다.

```python
this_list = list(input.split())
assert len(this_list) == 5, 'Input is not 5' # 조건이 참이 아닐 때 발생한다.
# AssertionError : Input is not 5 
```
