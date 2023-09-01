sql addition은 많이 안 쓴다.

workbench가 도와주는 친구이다.

execute the selected protion of the script or everything 번개

sql은 대소문지 구분하지 않는다. 

mySQL에 add diagram을 한후 err diagram을 추가하면 테이블을 만들 수 있다. ERD만들 수 있다.

schemas 클릭 후

create schema

기본 db는 3개가 있다. 

INSERT INTO

UPDATE SET

DELETE FROM

SQL 파일이 생성이 되었을 때 데이터베이스가 bold가 되어야한다. 그래야 선택된 것이다. 

`SELECT  [원하는 field col]  FROM 테이블;`

`SELECT * FROM 테이블 WHERE member_name = “이름”;`  이렇게 조건을 걸 수 있다.

여러개의 select를 사용하면 여러개의 탭이 생긴다.

### 데이터베이스 개체

인덱스, 뷰, 스토어드 프로시저, 트리거, 함수

인덱스는 데이터 조회할 때 결과나오는 속도를 빠르게 해준다. 뷰는 테이블의 일부를 제한적으로 표현할 때 사용한다. 스토어드 프로시저는 SQL에서 프로그래밍이 가능하도록 해주고 트리거는 잘못된 데이터가 들어가는 것을 막는다.

인덱스는 찾아보기 개념과 비슷하다. 

Execution Plan을 보면 Full Table Scan이라고 나온다. 전체 테이블 검색이라는 뜻이다. 

`create index idx_member_name on member(member_name);` 인덱스 만들기다

Non-Unique Key Lookup 이러면 인덱스가 생성된 것이다. 

뷰는 테이블과 동일한 성격의 데이터 베이스 개체이다. 실제 테이블과 연결된 가상테이블이다. 

```sql
create view member_view
as
	select * from member;
```

스토어드 프로시저는 여러개의 SQL문을 하나로 묶어서 편리하게 사용할 수 있다. 

```sql
delimiter //
create procedure myProc()
begin
select * from member where member_name="나훈아";
select * from product where product_name="삼각김밥";
end //
delimiter ;

Call myProc()
```
