## 클래스 메서드, 인스턴스 메서드, 정적 메서드

@  = 데코레이터, 공식문서에도 많이 쓰고 있어보인다. 코드가 줄어든다.

- 데코레이터(기존 기능에 붙인다.)

데코레이터는 함수를 꾸며서 새로운 기능을 부여한다.

```python
def ko_hello(name):
		print(f'안녕하세요{name}')

def en_hello(name):
		print(f'hi{name}')

def add_emoji(name,func):
		func(name)
		print('^_^;;')

add_emoji(name,en_hello) #함수를 넘겨서 활용한다. 하지만 길어졌다.

def emoji_decorator(func):
		def wrapper(name):
				func(name)
				print('^_^')
		return wrapper  #wrapper함수를 리턴하는 함수, 기능을 추가한다.

new_func = emoji_decorator(ko_hello) #새로운 함수를 생성한다. 기능을 추가한다.
emoji_decorator(ko_hello)('james') # 안녕하세요james \n ^_^

# 여기서 더편하게 하는 방법이 있다. 

@emoji_decorator
def fr_hello(name):
		print(f'bonjour{name}')

fr_hello('james') #bonjourjames \n ^_^
```

스태틱 메서드 : 클래스와 연관있는 매서드야… 각각의 클래스는 하나의 독립적인 객체다.  클래스 내부에 클래스의 기능이 있다. 이렇게 써야한다. 

해당 클래스 안쪽에 한정한다. self가 없다. 

즉 클래스, 인스턴스의 변수를 사용하지 않는다. 

```python
class Myclass:

		@staticmethod
		def static_method(arg1,...)
				return

		def method(self):
				return 'instance method'
		
		@classmethod
		def classmethod(cls):
				return 'class method'
		
		@staticmethod
		def staticmethod():
				return 'static method'

my_class = Myclass()
my_class.staticmethod() #문자열 리턴
```

## 객체지향의 개념 4가지 (물어보기 좋다)

---

추상화, 상속, 다형성, 캡슐화

추상화 : 핵심이 되는 부분만 추린다.

상속 : 코드의 재사용성을 높이면서 기능을 확장한다.

다형성 : 각자의 특성에 따라서 다른 결과 만들기

캡슐화 : 데이터를 보호하기

추상화 

### 상속 : 하위 클래스는 상위 클래스에 정의된 모든 속성, 행동 관계를 상속받는다.

---

```python
class ChildClass(ParentClass):

class BabyClass(ParentClass):

s1 = ChildClass()
isinstance(s1,ChildClass) #True
isinstance(s1, ParentClass) #True
isinstance(s1, BabyClass) #False

isinstance(s1, (ChildCalss,ParentClass)) # True
```

super()는 매우 중요하다. 자식클래스에서 부모클래스를 사용하고 싶을 때

```python
class Person:
		def __init__(self,name, age, number, email):

class Student(Person):
		def __init__(self, name, age, number, student_id):
				super().__init__(name,age,number, email)
				self.student_id = student_id
```

Super는 self가 안들어간다.

중복된 속성이나 메서드가 있을 때는 상속의 순서가 중요하다.

```python
class Person:
		def __init__(self, name):
				self.name = name

class Dad(Person):
		gene = 'XY'
		def walk(self):

class Mom(Person):
		gene = 'XX'
		def swim(self):

class FirstChild(Dad,Mom):
		def swim(self):
		def cry(self):

baby1 = FirstChild('아가') # Person의 __init__을 사용한다.
baby1.swim() #FirstChild의 Swim
baby1.gene() #Dad의 gene
```

mro 메서드 : 매우중요  어디서왔는지 보여준다

```python
baby1.mro # 상속받은 클래스들 순서대로
```

### 다형성 : 같은 것을 받아도 다른 모양이 나온다.

---

- 매서드 오버라이딩

부모클래스의 매서드를 자식클래스에서 수정할 수 있다.

같은 매서드를 재정의 해서 다르게 표현한다. 

```python
class Student(Person):
		def talk(self):
				super().talk() # Person의 talk를 실행한 후에
				print('something')

class Professor(Person):
		def talk(self):
				print('something???') # Person의 talk을 오버라이딩
```

### 캡슐화

---

클래스 안쪽 데이터는 클래스 안에서만 변경이 가능하다. 

파이썬은 완벽하게 캡슐화하지 않는다. 

외부에서 접근하는 것을 제어한다.

- 3가지 방법

Public Access Modifier : 모두 가능

Protected  Access Modifier : 상속관계만 가능

Private Access Modifier : 나만 가능

1. Public Access Modifier

언더바 없는 모든 메서드나 속성, 어디서나 호출가능하고 하위클래스에서 오버라이드 가능하다. 일반적으로 대부분이 퍼블릭

1. Protected  Access Modifier (파이썬은 개념적으로 존재하지만 불러지긴한다.)

언더바 한개로 시작하는 메서드나 속성, 

```python
class Person:
		def __init__(self,name,age):
				self.name = name
				sef._age = age
		def get_age(self):
				return self._age

p1 = Person('김싸피', 30)
print(p1.get_age()) # 30
print(p1._age) # 30 이거 되는데 하면 안된다.
```

1. Private Access Modifier

언더바 2개로 시작하는 메서드나 속성

클래스 내부에서만사용가능, 하위클래스 상속 및 호출 불가, 외부 호출 불가능

```python
class Person:
		def __init__(self,name,age):
				self.name = name
				sef.__age = age
		def get_age(self):
				return self.__age

p1 = Person('김싸피', 30)
print(p1.get_age()) # 30
print(p1.__age) # 오류
```

**매우 중요** : 클래스 내부에 self안쓰면 사라지는 변수다.  

### getter메서드와 setter 메서드

get : 얻기 set : 변경

@property 데코레이터 사용

@변수.setter 사용
