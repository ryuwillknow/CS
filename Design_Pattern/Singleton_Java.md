# Singleton in Java

구현

```java
class Singleton {
	private Singleton volatile singletonObject; // private으로 미리 객체를 선언한다.
	// 다른 스레드, 캐시에서 동시에 변경하는 것을 막기위해 volatile을 붙인다.
	
	private Sintleton () {}  // private 생성자로 새로운 생성을 막는다.

	public static Singleton getInstance() {  // getter를 사용할 때
		if (singletonObject == null) {  // 객체에 값이 없으면
			singletonObject = new Singleton();  // 새로운객체를 만들어준다.
		} 
		return singletonObject; // 객체를 반환해준다.
	}
}
```

제어자에서부터

제어자는 클래스 변수 메서드의 선언부에 함께 사용되어 부가적 의미를 부여한다.

제어자는 접근제어자(public, protected, default, private)와 그외(static, final, abstract, native, trasient, synchronized, volatile, strictfg)로 나뉜다. 모두 파지는 않고 중요하고 자주 나오는 것들만 알아봅시다.

1. static

매소드에 붙으면 인스턴스를 생성하지않고 호출이 가능한 static 매서드가 된다. (파이썬의 스태틱매소드랑 정의가 다르다. 가 아니라 같아!!!!!!!!! 그 링크가 잘못되었다. staticmethod 데코레이터 사용하면 같다. )

```java
class Good {
	static int num = 10;
}

public class Abc {
	public static void main(String[] arg) { 
		System.out.println(Good.num); // Good sss = new Good() 을 안했음
	}
}

# 10
// .java 파일 하나당 하나의 클래스가 있어야한다. 조심해야할 것은 같은 패키지 안에 있어야한다는 것이다.
// 물론 아닌 경우도 있다. .java 파일 안에 여러 클래스가 있을 수 있다.
// 이 경우에는 public class는 반드시 파일명과 같은 클래스에만 적용이 가능하다.
// 클래스 내부의 클래스에는 public을 사용할 수 있는데 .java파일의 최상위 클래스는 public이 단 하나여야하고 
// 그 클래스는 이름이 파일명과 같아야한다. main도 가지고 있어야?
```

1. final : final을 사용하면 변경이 불가능하다. ⇒ 매소드 클래스 변수 다 사용가능하다!

파이썬은 상수를 만들 수 없다. 

1. private public 등 접근 제어자 

private은 같은 클래스 내부에서만 접근이 가능하다. ⇒ 부모 클래스가 같으면 사용가능

public 제한 없다.

protected  같은 패키지 내에서 자손클래스에서 접근 가능하다

default 같은 패키지 내에서 접근 가능하다.

접근 가능하다는 것을 변수를 부르고 수정할 수 있다는 것

접근 제어하는 개념을 캡슐화라고 한다

```java
class parasite {
	
	class ex1 {
		private static int num = 999;
	}

	public static void main(String[] args) {
		System.out.println(ex1.num); // 999
		System.out.println(ex2.num); // 오류가 난다.
	}
}

class ex2 {
	private static int num = 777;
}
```

생성자와 private을 결합하면 인스턴스 생성을 막을 수도 있다.

++ 추가 정리 어이없지만 중요한 것 ++ inner class

```java
class InnerTest {

	class Wow {
		
	}

	static class Amazing {

	}
	
	public static void main(String[] args) {
		
		Wow hoho = new Wow();  // 이거 안됨 여기서 오류남
		Amazing qoqo = new Amazing(); // 이건 됨

		// inner클래스는 static을 붙여줘야지 독립적으로 인스턴스를 생성할 수 있다.
		// static 안붙이면 다음과 같이 인스턴스를 만들어야함

		InnerTest ioio = new InnerTest(); // 감싸고 있는 인스턴스 생성하고
		Wow hoho2 = ioio.new Wow(); // 인스턴스 내에서 인스턴스를 만들어야한다.

		// static이 없은 inner 클래스는 감싸고 있는 클래스의 클래스가 아닌 
		// 인스턴스의 클래스로 인식하기 때문
		// 따라서 독립적으로 쓰고 싶으면 static 붙이거나 밖으로 빼야한다.
	}
}
```

1. 오버라이딩, 오버로딩 (여기부터는 제어자 외 필요한 개념)

오버로딩 : 메소드명은 같지만 변수명이 다른 것,  파이썬은 없다.

```java
class Wow {
	static void print(int a) {
		System.out.println("int " + a);
	}
	static void print(String a) {
		System.out.println("String " + a);
	}

	public static void main(String[] args) {
		Wow.print(1);
		Wow.print("abcd");
	}
}

// int 1
// String abcd
```

오버라이딩 : 상속 받은 메소드를 자식 클래스에서 재정의하는 것, 이건 생략

1. 생성자

다른 생성자 호출할 때는 this를 사용한다.

```java
class Make {
	int something;
		
	Make() {
		// 얘가 생성자이다!
		this.somthing = 3; // 이렇게 해야한다.
		this(somthing);
	}

	Make(int a) {
		System.out.println("I did it!")
	}
}

Make good = new Make()

// 모든 클래스는 생성자가 있어야한다. 단 없을 경우 기본 클래스에서 상속 받는다.
// 1) new로 만들어지고 2) 생성자가 호출되어 실행된다. 
// 3) new의 결과로 만들어진 인스턴스의 주소거 good에 저장된다.
```

1. 쓰레드와 프로세스

프로세스는 실행중인 프로그램!

쓰레드는 실제 작업을 수행하는 개체 ⇒ 1개 이상이다! 2개 이상을 멀티 쓰레드라고 한다.

runnable 인터페이스를 상속 받는 방법과 thread를 상속 받는 법이 있다. 전자가 재사용성도 높고 일관성도 유지하기 편하다.

OS의 프로세스 스케줄러 : 쓰레드의 실행순서와 실행 시간을 결정한다. 

메소드로 쓰레드 우선순위 만들 수도 있고 그룹을 지을 수도 있다. Thread.sleep() 등 다양한 메소드로 쓰레드의 실행을 제어할 수도 있다.

쓰레드 동기화 : 현재 진행중인 작업을 다른 쓰레드가 간섭하지 못하도록 막는 것을 쓰레드 동기화라고 한다. 임계영역과 잠금이라는 개념이 중요하다. 

1. synchronized  ⇒ 임계영역 지정

```java
public synchronized void abc(int a) { // 메소드에 적용

	synchronized (this) { // 이렇게도 쓰인다! 객체의 참조변수
	}
} 
```

모든 객체는 lock을 한개씩 가지고 있다. synchronized는 가장 처음에 실행한 쓰레드에게 lock을 전달하게 만든다. 그렇게 되면 lock이 없는 객체는 lock이 있는 쓰레드만 접근이 가능하게 된다. synchronized 구간을 모두 실행하면 객체에게 lock을 반납한다.

synchronized를 남발하면 심각한 성능저하를 초래하므로 임계영역을 최소한으로 지정해야한다. 아니면 다른 방법을 사용하거나.

1. wait(), notify()

동기화 블록 내에서 사용가능한 함수이다.

wait()을 실행하면 lock을 반납하고 기다린다.

notify가 호출되면 lock은 하나이므로 다시 순서를 기다린다.

이외에도  java.util.concurrent.locks 패키지를 통해서 동기화를 할 수 있다.

1. volatile

캐시가 아닌 메모리에서 읽는다. 

프로세서마다 캐시가 있고 실행속도를 빠르게 하기 위해 메모리에서 캐시를 가져온다. 하지만 멀티코어의 경우 캐시의 변경사항이 메모리에 반영되기 전 다른 코어에서 변경이 생기면 원치않는 방향으로 코드가 흘러간다. 이를 방지하기위해 메모리를 캐시에 저장하지 않고 직접 읽어서 작업하기위해 volatile을 사용한다.
