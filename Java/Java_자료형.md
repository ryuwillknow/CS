# 자료형

기본자료형(원시) : 논리형 boolean 문자형 char  숫자형의 정수형 byte, short, int, long 숫자형의 실수형 float, double

```Java
int age; // 선언
age = 30; // 저장, 할당 초기화
int age = 30; // 초기화 선언 한번에
```

String은 참조형이기 때문에 변수 내에 주소값이 들어간다. 파이썬과 비슷


# 자료형 변환
형변환은 묵시적(작은 집에서 큰집 갈때), 명시적(큰집에서 작은집갈때)

```Java
int i = 100;
byte j = (byte) i;
```

비트부정 ~ 논리부정 !

나누기나 곱하기 항상 형변환을 생각하자.

float i = 3.2 안된다. 기본형은 int다

float i = (float) 3.2 로 해야한다. 형변환!

== !=  다 비슷한데 String은 equals()을 써야한다.

조건식 ? 식1 : 식2  삼항연산자!!
