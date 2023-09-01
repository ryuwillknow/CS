스프링으로 갑시다. 자바는 큰 트래픽을 다루기 좋다. 

스프링부트(Spring Boot)는 **자바의 웹 프레임워크**로 기존 스프링(Spring) 프레임워크에 톰캣 서버를 내장하고 여러 편의 기능들을 추가하여 꾸준한 인기를 누리고 있는 프레임워크이다.

IntelliJ IDEA supports a fully-functional integration with [Gradle](https://gradle.org/) that helps you automate your building process. CICD해주는  

Gradle은 Java, Kotlin, Groovy, C/C++와 같은 다양한 언어로 작성된 프로젝트를 빌드하기 위한 도구입니다.

JDK는 vendor에 따라 다르다. 

스프링 이니셜라이저를 통해 쉽게 할 수 있다.

JPA : 자바에서 관계형 데이터 베이스를 사용하는 방식을 정의한 인터페이스. JPA는 인터페이스 이고 ORM 프레임 워크를 선택해야한다. 하이버 네이트를 많이 사용한다. 

로그인 구현 : ID/PW OAuth2 JWT 토큰 인증방식등 

AWS 일래스틱 빈스토크를 활용해 배포한다. EC2 오토 스케일링 그룹, 로드밸런서, RDS AWS

깃허브 액션을 활용해 CI/CD 구현한다. 

그레이들과 메이븐의 차이 : 다양한 언어를 지원한다. 가독성이 좋다. 그래서 그레이들을 사용한다. 소스코드를 이용해서 실행가능한 어플리케이션을 생성하는 과정을 자동화하는 프로그램.

이렇게 만들면 그레이들 프로젝트를 만든 것이다. build.gradle을 수정하면 스프링부트 3프로젝트로 바꾼다. 

gradle은 kotlin 과 groovy문법이 다르다. 

gradle이 옆에 있다.

## Gradle 및 기본설정

스프링 부트 플러그 인과 스프링 의존성 자동관리 플러그인을 추가한다.

dependencies는 프로젝트를 개발하며 필요한 기능의 의존성을 입력한다. spring-boot-starter-web과 spring-boot-starter-test를 입력해둔다.
