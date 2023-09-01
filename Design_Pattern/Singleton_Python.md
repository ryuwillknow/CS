# Singleton in python

기본 : 특수 매서드 혹은 magic method라 불리는 것을 알아야한다.

```python
class Good:
	def __init__(self):
		pass
	def __str__(self):
		pass
	def __del__(self):
		pass

# 위처럼 클래스 내부에 정의된 함수 중 __로 시작하는 것들을 특수 메서드 혹은 매직 매서드라고 한다.
```

다양한 메소드는 [여기서 확인](https://docs.python.org/ko/3/reference/datamodel.html?highlight=__init__#object.__init__)하고 __init__과 __new__를 중점적으로 알아보자

둘을 알아보기 전 참고사항

```python
a = Good() 
# 이렇게 객체를 선언하면 Good 인스턴스를 1)만든 후 2)반환해서 메모리에 저장하고
# a가 반환된 인스턴스를 바인딩한다.
# 1) 2) 과정을 각각 __new__와 __init__이 수행한다.
```

먼저 __new__,

```python
class Plz:
	def __new__(cls):
		return cls.instance
```

이 친구는 새로운 객체를 만들 때 호출된다. 매우매우 특이하고 중요한 점은 반드시  cls(본인 클래스)의 인스턴스를 return해야한다는 점이다. 이 return이 없으면 __init__이 실행되지 않는다.

여기서 의문은 생성시 호출하는 함수 내부에서 어떻게 생성하냐는 것이다. 여기서 또 다시 클래스를 생성하면 무한 재귀가 된다.

이 의문의 해결법은 super()에 있다. super()는 부모 클래스를 가리키는 키워드이다. 지금 선언한 Plz는 아무것도 상속 받지 않았는데? 어떻게 부모클래스가 있지라고 생각했었는데 모든 것이 객체라고 생각하면 금방 오해가 풀림

Plz라는 클래스도 object(얘는 JS의 object아님)라는 클래스의 객체인거임. 생각해보면 class정의 할 때 __init__ __new__ 정의 하지 않아도 잘 돌아갔었다. 이는 우리가 만들었던 객체가 가장 조상, 파이썬에 내장되어 있는, 가장 기본이 되는 object의 매직 메소드를 상속 받았기 때문이다. 우리가 __init__을 정의했던 것은 없던 것을 있게 만든 것이 아니라 **오버라이딩** 한 것. 물론 __str__ 같은 것은 기본 object class에 없어서 새로 정의해줘야한다.

여튼, Plz 클래스에 __new__메소드 내부에서 인스턴스(객체)를 만들려면 다음과 같이 한다.

```python
class Plz:  # 파이썬2 는 class Plz(object)로 해줘야한다. 파이썬 3은 생략가능
	def __new__(cls, data): #__init__ 과 맞춰야함
		cls.instance = super().__new__(cls) # 근데 의문은 __new__()에 왜 cls가?
		# 아마도 __new__() 메소드 자체가 안의 인자의 인스턴스를 만드는 것이기 때문에
		# __new__의 위치가 중요하지 않다. 그냥 조상꺼 빌려쓰는 느낌, 인자의 인스턴스를 만든다.
		return cls.instance

# 이렇게 클래스의 인스턴스를 반환하면 __init__이 실행된다.

	def __init__(self, data):  # 여기에 인자 추가하기도 한다 얘가 생성자
		self.data = data

# __init__ 이 실행되면 데이터를 넣고 '알아서' __new__에서 만든 인스턴스를 반환해줌 
```

여기서 추가사항 : 내장함수 hasattr

```python
hasattr(cls, '변수 혹은 메서드 명') => bool
# 클래스 내부에 두번째 인자가 있는가?

class clscls:
	a=1
	def b(self):
		pass

hasattr(clscls, 'a') # True
hasattr(clscls, 'b') # True
hasattr(clscls, 'c') # False

# 자매품
getattr(clscls, 'a') # 1
```

이걸로 파이썬의 싱글톤 구현이 가능하다.
