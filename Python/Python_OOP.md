#OOP

클래스와 인스턴스 Class instance

## 절차 지향 프로그래밍

---

절차 지향 프로그래밍은 유기적인 흐름이 다 드러난다.

실행이 빠르다.

한 부분 고장나면 다 고쳐야한다.

→ 여러가지를 조립하는 방식으로 개발하다 → 객체지향 프로그래밍

## 객체 지향 프로그래밍

---

데이터와 기능을 분리. 추상화된 구조

기능 = 메서드

객체를 잘 만들면 계속 사용가능하다.

개발 용이성, 유지보수편의성, 신뢰성 상승

처음 설계시 많은 노력과 시간이 필요함

클래스를 정의한 것을 토대로 메모리에 할당된 것

하나의 객체에는 데이터와 메서드가 있다.

객체 = instance 설계도 = class

## 문법

---

```python
class MyClass: #클래스 생성
	pass

my_instance = MyClass() #인스턴스 생성

my_instance.my_method() #매서드 생성

my_instance.attribute #속성접근 그 데이터에 접근하고자 할 때.. 생소한데 괜찮다.
```

## 객체 비교하기

---

- == : 동등한  즉 내용이 같은 경우만 True
- is 는 동일한 객체를 가리키는 경우 True - 주소까지 같아야한다.

```python
a = [1,2,3]
b = [1,2,3]

print(a == b, a is b) #True False

a = [1, 2, 3]
a = b
print(a == b, a is b) #True True
```

## OOP문법

---

클래스를 정의하면 클래스에 해당하는 이름 공간이 생성

인스턴스를 만들면 인스턴스 객체가 생성되고 이름 공각 생성

인스턴스에서 특정 속성을 접근하면 인스턴스 클래스 순으로 탐색

```python
class Person:
	name = 'unknown' #클래스 내부에 정의된 변수
	def talk(self):
		print(self.name)
p1 = Person()
p1.talk() # unknown

p2 = Person()
p2.name = 'Kim'
p2.talk() # Kim

print(Person.name)
print(p1.name)
print(p2.name)

p2.age = 23 #도 가능하다
```

- 인스턴스 변수

인스턴스가 개인적으로 가지고 있는 속성

생성자 메서드에서 self.<name>으로 정의 가능

```python
class Person:
    def __init__(self, name): # __init__ 은 생성할 때 값을 받아서 어디에 넣어주세요.
        self.name = name  # Person이라는 클래스의 인스턴스를 생성할 때 변수를 받고 싶을 때
john = Person('john') # 생성시 불려지는 함수가 언더 이닛(생성자이다)
```

언더 이닛을 생성자라고 말한다.

```python
class Person:
		count = 0
    def __init__(self, name): #self는 파이썬이 자동으로 넣어준다
				self.name = name
				Person.count += 1 #인스턴스 생성시 함수를 실행한다. 위의 변수는 실행하지 않는다.
```

- self

self는 인스턴스 자기자신.   (self는 파이썬이 자동으로 넣어준다.)

## OOP 메서드

---

클래스 메서드과 인스턴스 메서드가 다르다.

인스턴스는 클래스와 인스턴스 메서드를 모두 사용가능하다.

클래스는 클래스 메서드만 사용가능하다.

```python
class Person:

		def talk(self):
				print('Hi')

		def eat(self, food):
				print(f'{food}를 냠냠')  # 위의 두개는 인스턴스 메서드이다. self가 들어갔으므로
#사실 __init__도 들어가 있다. 보이지 않을 뿐
```

- 메서드의 종류 3가지

인스턴스 메서드 - 가장 흔하다. 첫번째 self가 자동으로 전달됨 그걸 self로 받는다. (다른 단어로 써도 작동한다.!!!!! 역시!!!!)

클래스 메서드 - 인스턴스 상관없이 클래스변수 사용한다. 지금은 진짜 조금 쓰인다. self 필요없다

정적 메서드 - 인스턴스, 클래스 모두 필요없을 때  지금은 거의 없다.

**매직 메서드** - 더블 언더스코어가 있는 메서드 . 특정 상황에 자동으로 불리는 메서드

```python
__init__ # 인스턴스 생성시 자동으로
__str__ # 클래스를 문자열로 만들면 어떻게 할거야?

class Person:
    def __init__(self, name, age):
				pass
		def __str__(self):
				return '이 클래스를 문자열로 표현하면 이겁니다'
		def __gt__(self,other): #비교할 때 자동으로 불러준다.
		
		def __len__(self)__ # len나왔을 때 어떤 걸로?

dien = Person()
print(dien)
```

**클래스 매서드**

호출시 첫번째 인자로 클래스가 전달됨 (cls로 받아라)

```python
class MYclass:
		@classmethod
		def class_method(cls)
					pass
```

```python
class Person:
		count = 0
		def __init__(self, name):
				self.name = name
				Person.count += 1
		@classmethod
		def number_of_population(cls):
				print(f'인구수는 {cls.count}입니다.')
person1 = Person('아이유')
person2 = Person('이찬혁')

Person.number_of_population() #2
person1.number_of_population() #2
person2.number_of_population() #2

#인스턴스랑 관련이 없다. 클래스의 무언가를 할 뿐이다.
print(person1.count) # 2이다!!! 클래스의 변수!
```

**인스턴스는 목적어 없이 쓰면 안된다. 클래스의 인스턴스라고 말해야한다.**

## OOP 추가사항

---
