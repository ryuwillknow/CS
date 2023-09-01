## SELECT 문에 대해서

```sql
DROP DATABASE IF EXISTS market_db; // 있으면 삭제하라
CREATE DATABASE market_db; // db를 만들라

use market_db

create table member -- 회원 테이블(member)
(mem_id char(8) NOT NULL PRIMARY KEY,
 mem_name  VARCHAR(10) NOT NULL,
 mem_number INT NOT NULL,
 addr CHAR(2) NOT NULL,
 phone1 CHAR(3),
 phone2 CHAR(8),
 height SMALLINT,
 debut_date DATE
 );

-- 이게 주석이고 쉽표를 매우 조심해야한다. 

CREATE TABLE buy
 ( num INT AUTO_INCREMENT NOT NULL PRIMARY KEY,
   mem_id CHAR(8) NOT NULL,
   prod_name CHAR(6) NOT NULL,
   group_name CHAR(4),
   price INT NOT NULL,
   amount SMALLINT NOT NULL,
   FOREIGN KEY (mem_id) REFERENCES member(mem_id)
   );

Foreign key col references table(col)구문을 기억하자. 

INSERT INTO buy VALUES(NULL, 'TWC', '지갑', NULL, 30, 2);
```

여기서 참고사항 `INT` 다음에 `AUTO_INCREMENT`가 와야한다. `AUTO_INCREMENT`가 먼저 오면 안된다.

Error Code 1452은 외래 키(Foreign Key) 제약 조건을 위반하는 경우 발생합니다. 이 오류를 해결하기 위해 다음 단계를 따를 수 있습니다:

Error Code: 1366. Incorrect string value: '\xED\x8A\xB8\xEC\x99\x80...' for column 'mem_name' at row 1  ⇒ utf 8 으로 바꿔줘야한다.

`ALTER TABLE buy convert to character set utf8;`

Error Code: 1833. Cannot change column 'mem_id': used in a foreign key constraint 'buy_ibfk_1' of table 'market_db.buy’ ⇒ 외래키는 변경이 불가능하다

`set foreign_key_checks=0;`

## SELECT

테이블에서 데이터를 가져올 때 사용하는 예약어이다.

`SELECT` 다음에는 열이 나온다. *는 전체를 의미한다.  

`FROM`  다음에는 테이블이 나온다.

테이블은 일반적으로 database.table의 형태로 적어야하는데 use문을 사용했으므로 

괄호를 쓰면 안된다?? 왜?? INSERT 문과 CREAT TABLE 문에서 사용?

`where` 은 조건을 만들어준다. 문자열을 `“이렇게 표현”`

관계연산자, 논리연산자를 활용해서 where의 조건을 만들어줄 수 있다.

`AND OR`

`WHERE height BETWEEN 160 AND 165`

`WHERE height IN (164, 165, 168)`

`WHERE name LIKE “%우”`   %는 아무거나 _는 한 칸

**서브쿼리**

`SELECT name FROM table WHERE name = “james”;`

`SELECT * FROM table WHERE first_name IN(SELECT name FROM table WHERE name = “james”);`

괄호로 그 값 혹은 배열을 묶어줄 수 있다.

`SELECT * FROM member ORDER BY height DESC`  역순으로

단 `ORDER BY` 는 `WHERE` 과 순서를 조심해야한다.

`ORDER BY age ASC, height ASC` 처음 거 적용 후 같은 것들은 두번쨰로 정렬한다.

`LIMIT 5` 개수를 제한한다. `LIMIT 3 5`  3번째에서 5번째의 것들만

`DISTINCT` 중복을 제거해준다. 열, column에 넣어준다.

`SELECT DISTINCT name FROM table`

`GROUP BY` 는 같은 내용의 열을 묶어준다. 주로 집계함수와 함께 사용한다.

`COUNT, SUM, AVG, MIN, MAX, COUNT(DISTINCT)`   `count` 는 `null`을 제외한다.

집계함수 안쓰면 첫번째만 보여준다. 

`WHERE`을 `GROUP BY`의 조건절로 사용할 수 없다.  `GROUP BY`의 조건절은 `HAVING` 뿐이다. 여기 안에서 집계함수를 활용해 조건을 부여할 수 있다. 

`ORDER BY`는 막 사용가능하다.

`DROP TABLE IF EXISTS market_db.toy;`

`CREATE TABLE market_db.toy (toy_id INT, toy_name CHAR(12), age INT);`

`ALTER TABLE table AUTO_INCREMENT=100;`

하지만 `AUTO_INCREMENT`로 지정된 것은 만드시 KEY여야한다.

`Error Code: 1075. Incorrect table definition; there can be only one auto column and it must be defined as a key`

`SET @@AUTO_INCREMENT_INCREMENT = 3;`이러면 3씩 증가한다.  @@어쩌구 친구는 환경변수이다.

`SHOW global variables;`

`DESC table`  표로 보여준다

**INSERT**

`INSERT INTO toy VALUES (NULL, "JAMES" , 14);`

`INSERT INTO table1 SELECT * FROM table2`  이렇게 하면 다른 테이블 값 쉽게 가져올 수 있다.

**UPDATE**

WORKBENCH는 `UPDATE`를 허용하지 않아서 설정을 해줘야한다. 재시작까지!

`UPDATE market_db.toy SET age = 16;`  전부 바꾸기
`UPDATE market_db.toy SET age = 18 WHERE toy_name = "JOY";`

**DELETE**

`DELETE FROM table WHERE ()` 

`LIMIT` 도 사용가능

`DELETE` 는 오래 걸림, `DROP TABLE`은 table을 다 삭제한다, `TRUNCATE`는 내용만 삭제한다. 구조는 남긴다.

**Bash로 DB 다루기**

환경변수로 추가하기, 도커는 바로 되는 듯

`mysql -uroot -p1234 market_db;`  use 인듯

`show tables from market_db;`

`show databases;` 등등
