DBMS 데이터 베이스를 관리하는 소프트웨어이다. RDBMS는 관계형 데이터 베이스를 다루는 소프트 웨어이다. 

H2와 MySql을 다룰 것이다. H2는 자바로 작성되는 RDBMS이다.  인메모리 관계형 데이터 베이스이다.

ORM은 객체와 데이터베이스를 연결하는 프로그래밍 기법이다. 장점은 SQL을 직접 작성하지 않는다. 객체지향적으로 코드를 작성할 수 있기 때문에 비즈니스 로직에 집중할 수 있다. MySQL에서 PostgreSQL로 전환하더라도 추가로 드는 작업이 없다.

단점 : 프로젝트 복잡성이 커지면 사용 난이도가 올라간다. 복잡하고 무거운 쿼리는 orm으로 해결이 불가능 한 경우도 있다.

JPA는 관계형 데이터 베이스 사용하는 방식을 정의한 인터페이스이다. 실제 사용을 위해서는 ORM 프레임 워크를 추가적으로 사용해야한다. 대표적으로 하이버네이트가 있다. 내부적으로는 JDBC API를 사용한다.