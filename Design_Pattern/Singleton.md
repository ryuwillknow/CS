### 1. 싱글톤 패턴 (생성패턴)

하나의 클래스에 오직 하나의 인스턴스를 갖는 패턴

싱글톤 자바에서 구현하고자 했으나 쓰레드, 생성자 개념이 중요하다. 배우고 채우기→ 파이썬도 쓰레드 개념이 있더라

싱글톤 파이썬에서 구현

```python
class Singleton(object):
    def __new__(cls, *args, **kwargs):
        if not hasattr(cls, "_instance"):         # 클래스 객체에 _instance 속성이 없다면
            print("__new__ is called\n")
            cls._instance = super().__new__(cls)  # 클래스의 객체를 생성하고 _instance로 바인딩
        return cls._instance                      # _instance를 리턴 => 이게 뭐시여

    def __init__(self, data):
        cls = type(self)
        if not hasattr(cls, "_init"):             # 클래스 객체에 _init 속성이 없다면
            print("__init__ is called\n")
            self.data = data
            cls._init = True

s1 = Singleton(3)
# __new__ is called
# __init__ is called
s2 = Singleton(4)
# 아무것도 안 뜸
print(s1.data)
# 3
print(s2.data)
# 3 s2의 data는 s1.data의 데이터를 가리킨다. 즉 객체 선언은 되지만 하나의 인스턴스이다. 하나의 메모리를 가리킨다.
```

싱글톤 자바에서 구현

```java
class Singleton {
	private Singleton volatile singletonObject; // private으로 미리 객체를 선언한다.
	// 다른 스레드, 캐시에서 동시에 변경하는 것을 막기위해 volatile을 붙인다.
	
	private Sintleton () {}  // private 생성자로 new를 막는다.

	public static Singleton getInstance() {  // getter를 사용할 때
		if (singletonObject == null) {  // 객체에 값이 없으면
			singletonObject = new Singleton();  // 새로운객체를 만들어준다.
		} 
		return singletonObject; // 객체를 반환해준다.
	}
}
```

기능

오직 하나의 인스턴스만 사용하기 위해서 만든다. 

사용범위 위치
