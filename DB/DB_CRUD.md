# DB

진짜 데이터를 CRUD할 것이다.

데이터를 조작할 것이다.

### Aggregate function

집계함수이다. 최대값 최소값, 평균 합계 개수 계산해준다.

AVG() COUNT() MAX() MIN() SUM()

```sql
--전체 개수 
SELECT COUNT(*) FROM users;  
```

데이터 베이스에서 직접 계산하는게 더 효율적이다. raw정보를 가져와서 하는 것보다 낫다. 데이터베이스가 최적화가 되어있기 때문이다.

지역별 평균은 어떻게 하나? 여러개의 SELECT문?

```sql
--지역 조회
SELECT DISTINCT country FROM users;

-- 지역과 평균
SELECT country, avg(balance) FROM users WHERE country="전라북도";

-- GROUP BY 사용하면 특정
SELECT country, avg(balance) FROM users GROUP BY country;
```

결과가 달라요 왜?

COUNT는 현재 어떻게 해도 똑같다. 

단 COUNT(*)은 NULL도 센다.

AS로 키워드 설정 가능하다. 원본이 변경되는 것은 아니다. 조회가 바뀌는 것이다.

### 데이터를 바꾸기!!

INSERT, UPDATE, DELETE

```sql
--INSERT INTO
INSERT INTO classmate (name, age, address) VALUES('제임스', 23,'Los Angeles');
INSERT INTO classmate VALUES('제임스', 23,'Los Angeles');
INSERT INTO classmate VALUES('놀란', 50, '영국'), ('봉준호', 17, '서울'), ('페이커', 7,'서울'), ('바보바보', 18347, '우주');

--UPDATE SET WHERE   (SET으로 값을 수정하고, WHERE로 조건)
UPDATE classmate SET name='바보의 왕',  address='우주의 블랙홀' WHERE rowid=5;

--DELETE
DELETE FROM classmate WHERE rowid = 5;
DELETE FROM classmate WHERE name LIKE '%영%';

--전체 삭제  DROP TABLE?
DELETE FROM classmate 
```

사실 데이터베이스는 배워야할 부분이 엄청나게 많다. 

데이터 베이스에 접근할 수 있는 권한기능이 있는 경우가 있다. SQLite는 없다.

실무에서는 데이터를 날리지 않고 지울 수 있는 방법이 있다. soft delete. 그럼 hard delete도 있다. 지금까지 hard delete이다. 

column에 is_deleted를 만들어주는 것이다. 

### 정규형

테이블을 나누는 이유 : 간단화하기 위해 무결성 체크가 어렵다  데이터 베이스의 중복을 줄이기 위해

예를들어 배송완료 배송중 이런 거를 할때 age, address가 계속 겹치기 때문이다. 

어떻게 나눠야 잘 나누는 걸까?

중복을 최소화하고 일관성과 무결성을 보장하기 위해 데이터를 정규형으로 만드는 것을 정규화라고 한다.

관계형 데이터베이스는 6개의 정규형이 있다.

제 1정규형, 제 2정규형, 제 3정규형을 살짝 알아보자.

### 제 1 정규형

하나의 속성값이 복수형을 가지면 안된다.

취미에 여러개를 만들지 말라는 것

### 제 2 정규형

테이블의 테마와 관련없는 컬럼은 다른 테이블과 분리하는 것

테이블의 함수적 종속성을 제거한 것  종속되어있는 속성을 새로운 테이블로 만들어준다. 

무엇을 고유하게? 어떻게 묶을까? 어떻게 PK를 만들까

PK만들고 밖으로 뺀다.  짱찾아서 묶기

### 제 3 정규형

다른 속성에 의존하는 속성은 따로 분리할 것

## JOIN

테이블은 여러 개로 나눠진다.

조회를 하려면 여러개를 1개로 만들어야한다. == 테이블을 연결해야한다. == JOIN

JOIN은 여러가지 방법이 있다.

FROM 여러개를 할 수 있다.!!!!

INNER JOIN 많이 쓰면 안된다.

# 자습

```sql
SELECT
FROM
GROUP BY
ORDER BY COUNT() DESC
```

is not null
