# 중간 정리 파이썬과 자바의 다른 점⭐

파이썬과 자바의 클래스 개념은 비슷한듯 다르다.

1.  자바의 static변수 == 파이썬 class 변수 ==  파이썬 static 변수

하지만 선언 방법이 다르다. 

자바는 class 내부 변수에 static이 붙은 변수를 static변수로 선언

```java
class Test {
	public static void main(String[] args) {
		
		class Hi {
			static int num = 10; // static 변수 : 인스턴스 안 만들어도 사용가능
			int num2 = 12; // instance 변수 : 인스턴스를 만들어야 접근이 가능하다.
			// 인스턴스 변수는 각각 인스턴스 마다 생성된다.		
		}

		System.out.println(Hi.num);  // static 변수 호출  결과 값 : 10

		Hi one = new Hi();
		Hi two = new Hi();
		two.num2 = two.num2 + 1;
		System.out.println(one.num2);  // 인스턴스 변수 호출  결과 값 : 12
		System.out.println(two.num2);  // 인스턴스 변수 호출  결과 값 : 13
	}
}
```

파이썬은 class내부에 변수 선언 위치에 따라서 갈린다. 

중요한 것은 인스턴스 변수는 인스턴스 메소드로만 접근 가능하다.

self가 인스턴스이기 때문이다!!!!

```python
class Hi ():
	why = 0 # 얘가 class 변수 and static 변수  그냥 메소드 밖에 선언해주면 됨

	def __init__ (self, data):  # 얘는 인스턴스 메서드, 조금 있다가 설명함
		self.abc = 3 # 얘가 인스턴스 변수
		self.data = data  # 얘가 인스턴스 변수
	def create(self):
		self.data2 = 3 # 꼭 생성자에서만 생성하는 것은 아님. 

	bye = 4 # 얘도 class 변수 and static 변수

print(Hi.why) # 0
print(Hi.bye) # 0
three = Hi(5)
print(three.abc) # 3
print(three.data) # 5
```

1. 자바의 static 메서드는 class 메서드와 static 메서드를 더한 개념인듯? 명확하진 않음 일단 ㄱㄱ

자바는 파이썬과 다르게 메서드 내에서 인스턴스 혹은 클래스 변수를 만들 수 없다.

매소드 내에서는 static 사용불가. 지역변수일 뿐이다!!! final만 허용된다고 한다!

파이썬은 메소드 내에서 인스턴스 변수 생성 가능하다.

```java
class Javava {

	class Coco {
		static void says (String words) {
			System.out.println(words);
		}
	}

	public static void main(String[] args) {
		Coco.says("Do not leave me");  // 반드시 쌍따옴표
	}
}
```

파이썬은 static 매소드처럼 인스턴스 없이 클래스에서 수행가능한 메소드가 두종류가 있다. 하나는 class 메소드이고 다른 하나는 static메소드이다.

```python
class Moon:
	rise = 0

	def __init__(self, movie):
		self.movie = movie

	def king (self, boy): # 인스턴스 메소드
		self.boy = boy  # 인스턴스 변수 생성
		type(self).rrrise = 12 # 이렇게 클래스 변수도 생성가능, 클래스로 접근 가능
	
	@classmethod
	def dom (cls, girl):
		cls.rise += 1
		cls.rrise = 3  # 클래스 변수 생성

	@staticmethod
	def good (good):
		print(good)

# 사실 클래스 변수는 막 생성이 가능하다.
Moon.wow = 3 # 해도 생성이 된다.
# 파이썬이 이런 부분이 아쉽다. java는 클래스 변수는 클래스 내부에서만 생성이 가능하기 때문이다.
```

인스턴스 메소드는 첫인자로 인스턴스 자신을 받는다. 관용적으로 self라 쓴다.

클래스 메소드는 첫인자로 클래스를 받는다. 관용적으로 cls라 쓴다.

스태틱 메소드는 첫인자로 아무것도 받지 않는다. 

클래스 메소드 스태틱 메소드는 모두 인스턴스 없이 호출이 가능하다! 

결론 : java와 python은 class를 다루는 구조가 달라 둘을 동시에 비교할 수 없다. 각각을 이해야한다.

+++ java와 python의 결정적 차이 : python은 인스턴스 변수, 클래스 변수 막생성가능 진짜 막!! vs  java는 class 코드 내부에서만 생성가능!!!+++

⇒ 이래서 파이썬이 모듈화가 부족하다고 한다. 하지만 이를 극복하는 매직 매서드가 있다.

__setattr__ !  + 이런 모듈화를 getter와 setter가 해준다고 하는데 알아보자.  

getter setter는 메소드로 접근권한을 지정 ⇒ 조건 더 만들어준다. 큰의미가 없기는 해…
