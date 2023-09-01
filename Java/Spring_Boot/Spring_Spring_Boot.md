## 스프링과 스프링 부트

스프링은 어플리케이션 환경을 수동으로 구성해야하지만 스프링 부트는 스프링 코어와 스프링 MVD의 모든 기능을 자동으로 로드해준다.

스프링은 톰켓 제티와 같은 WAS에서 배포된다. WAS는 웹어플리케이션을 실행하기 위한 장치이다. 하지만 스프링 부트는 WAS를 내장하고 있다. 그래서 jar파일만 만들면 어플리케이션을 실행할 수 있다.

IoC/DI 는 객체를 생성하지 않고 할당한다. 빈이라는 스프링 컨테이너에서 객체를 주입했기 때문이다.  @Autowired 와 같은 에너테이션으로 주입한다. 그리고 클래스에 @Component 애너테이션을 붙이면 그 클래스는 빈으로 등록된다. MyBean은  myBean이 된다.

이 외에도 AOP, PSA(이식가능한 서비스 추상화) PSA는 어떤 기술을 사용하던 일관적으로 데이터베이스에 접근하도록 인터페이스를 지원한다. ORM으로 JPA, MyBatis, JDBC 같은 것들이 있따. WAS의 톰캣도 같은 PSA의 예시이다.

@GetMapping은 get요청시 반환하는 함수

스프링 부트 스타터는 의존성이 모여있는 그룹이다. 

스프링 부트는 여러부분을 미리 설정해주는데 이를 autoconfigure에서 확인 가능하다.

스프링부트 2는 자바 8이상 스프링부트3는 자바 17이상

자바 17은 “”” “”” 로 여러줄 표현가능  formatted로 쉽게 파싱 가능  record 기능으로 데이터를 더 빠르게 전달 할 수 있다. private final로 저장가능하다. instanceof 로 패턴 매칭이 쉬워진다.

configuration 설정파일 등록  repository ORM 매핑  Controller RestController 라우터 Service 비즈니스 로직

컨트롤러 - 프레젠테이션 계층, 서비스- 비즈니스 계층, 리포지토리 - 퍼시스턴스 계층

main에 코드 작성한다. test는 테스트 목적 코드와 리소스 파일이 들어있다.

build.gradle 빌드를 설정하는 파일이다. settings.gradle은 빌드할 프로젝트의 정보를 설정하는 파일

main 디렉토리에는 java와 resources가 있다. resource 디렉터리에 HTML와 같은 뷰파일을 넣는다. css는 static폴더에 넣는다. application.yml 파일은 스프링 부트 서버가 실행되면 자동으로 로딩되는 파일이다. 데이터 베이스의 설정 정보, 로깅 설정 정보등이 들어갈 수 있다. 

롬복 : 반복 메서드 작성 작업을 줄여주는 라이브러리

H2 : 인메모리 데이터베이스

의존성 추가하기 : build.gradle dependencies에 추가하기 + 오른 쪽 Gradle에서 새로구침을 누르면 다운 받는다!!!

controller, service, repository

alt + enter로 오류 확인가능

jakarta

인메모리 데이터 베이스 H2는 어플리케이션이 새로 실행할 때마다 데이터가 사라져 불편하다. resource에 data.sql 파일에 쿼리를 작성해둔다.

스프링 부트 요청 등답 과정을 한 방에 이해하기

포스트 맨은 톰캣에게 /test GET을 요청한다.

디스패처 서블릿이 URL을 분석하고 요청할 컨트롤러를 찾아 요청을 전달한다.

메서드를 통해 데이터를 가져온다.

view리졸버는 json, xml, html을 만들어서
