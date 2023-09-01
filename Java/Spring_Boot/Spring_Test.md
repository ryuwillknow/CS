## 테스트 코드

다양한 방식이 있다. given, when, then 패턴을 사용할 것이다.

스프링 부트는 spring-boot-starter-test에 테스트를 위한 도구가 모여있다.

JUnit, Spring Test & Spring Boot Test, AssertJ(검증문인 어설션을 작성하는데 사용하는 라이브러리)

테스트는 각각 객체를 만드렁준다.

AssertJ 를 사용한 코드는 가독성이 좋다

```java
assertThat(a + b).isEqualTo(sum);
isNotEqualTo
contains
doesNotContain
startsWith
endsWith
isEmpty
isNotEmpty
isPositive
isNegative
isGreaterThan
isLessThan
```

원하는 클래스에 커서를 놓고 alt enter를 하면 create test 가능하다.

MockMvc는 배포하지 않아도 테스트용 MVC환경을 만들어 요청 및 전송, 응답 기능을 제공하는 유틸리티 클래스이다. 

given 멤버 저장하고 when  리스트 조회하는 API 호출하고 then 응답 코드가 200이면 OK 요서가 같은지 확인
