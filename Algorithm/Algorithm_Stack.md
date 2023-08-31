# Stack

자료구조와 파이썬의 자료구조(list, dictionary…)가 다르다.

선형구조를 갖는다. 

후입선출 LIFO  Last In First Out : 나중에 들어간 애가 먼저나오는 자료구조.

1, 2, 3 순으로 넣으면 3, 2, 1 순으로 꺼낸다. - 넣는다는 개념이 다르다.

배열을 사용할 수 있다.

스택에 마지막에 삽입된 원소의 위치를 top이라 부른다.

## 연산

push : 삽입 저장소에 자료를 저장한다.

pop : 저장소에서 자료를 꺼낸다. 꺼낸 자료는 삽입한 자료의 역순으로 꺼낸다. - 삭제라고 한다.

isEmpty : 스택이 공백인지 아닌지를 확인하는 연산

peek : top에 있는 item(원소)를 반환하는 연산

push 알고리즘

```python
def push(item) :
	s.append(item) # 대신 느리다.  일반적으로 스택의 크기를 먼저 구현한다.

def push(item, size)
	global top
	top += 1
	if top == size:
		print("overflow!") # 이상적이지는 않다. stack의 크기를 잘못 생각했기 때문이다.
	else:
		stack[top] = item

size = 10
stack = [0] * size
top = -1

push(10, size)
top += 1
stack[top] = 20
```

pop 알고리즘

```python
def pop():
	global top
	if top == -1:
		print('underflow')
		return 0
	else:
		top = -1
		return stack[top + 1]  #삭제가 아니라 그냥 그 자리에 있는거다.

print(pop())

if top > -1:
	top -= 1
	print(stack[top + 1])
```

## 스택 고려사항

1차원 배열은 변경이 쉽지만 크기 변경이 어렵다.

append 는 메모리 상에 한줄로 쭉 있지 않는다.

동적으로 할당하기 때문이다. 

배열이 메모리 상에 물리적으로 연속으로 있는게 중요하다!!!

## 스택의 응용

괄호 검사

여는 괄호가 나오면 push하기 

닫힌 괄호가 나오면 pop해서 비교하기

더 괄호가 없고 stack에 있으면 오류

닫는 괄호가 있는데 stack에 없으면 오류

Function call

후입선출 구조의 스택을 이용하여 수행순서 관리

함수호출이 발생할 때 호출한 함수 수행에 필요한 지역변수, 매개변스 및 복귀할 주소 등 스택 ㅍ레임에 저장하여 시스템 스택에 삽입

## 일반 알고리즘에서는

리스트 하나로 가능?

알고리즘의 전체를 파악해야한다. 어떤 과정을 거치는지를 알아야지 이것을 개선할 알고리즘을 발견할 수 있다.  # 이거 연습 많이 하자.

스택을 구현하지 않아도 메모리는 스택의 형태가 있다. 순서가 생긴다.

## 재귀 호출

예시

```python
def f(i, k) # i단계 k목표
	if i == k:
		print(B)
		return
	else:
		b[i] = a[i]
		f(i + 1, k)
a = [10, 20, 30]
b = [0] * 3
f(0, 3)

# 1000개 복사하면 RecursionError가 생긴다. 최대 깊이를 넘었으므로
```
