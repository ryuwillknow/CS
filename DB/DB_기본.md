# DB 기본

데이터는 저장이나 처리에 효율적인 형태로 변환된 정보

대부분 파일을 통해 데이터를 관리한다.

엑셀은 무한하게 커질 수 없음 100만행이 최대다

데이터 보안이 부족하고

데이터 무결성이 아쉽다.

- 파일은 한계가 있으니 데이터 베이스로 데이터를 저장한다.

데이터베이스는 조직화되어있는 데이터의 모음이다.

DBMS : Database Management System

데이터를 모으고 꺼내쓸 수 있는 소프트웨어

DBMS 종류 : SQLite MySQL ORACLE mongoDB redis PostgreSQL MariaDB elasticsearch

데이터 베이스는 SQL vs NoSQL  관계형 vs 비관계형

관계형 = 표 형식

관계형 데이터베이스의 한계를 극복하기 위해 만든 유연한 데이터 베이스

관계형 데이터 베이스의 한계 : 추후에 정보를 넣기가 어렵다. 수정이 어렵다. 틀이 정해져있다.

비관계형 데이터 베이스는 서브 데이터베이스로 둔다.

빠른 처리가 필요하거나 잠시 둘 때 비관계형 데이터 베이스에 넣는다.

SQL : Streuctured Query Language  데이터를 조작하는 언어

데이터베이스의 모든 것을 알려고 하지말자

회원가입, 회원탈퇴, 프로필 조회, 프로필 수정, 새로운 피드 작성 좋아요 팔로우 등 CRUD의 반복이다. 단, 좋아요는 create이다… Delete

### 관계형 데이터베이스(RDB)

데이터의 무결성을 유지하는데 장점이 있음 : 정확성, 일관성

### 관계형 데이터 베이스의 구조

Table, Field, Record, Schema, Primary Key, Foreign Key

1. 스키마

테이블의 구조이다. 모델에서 정의했던 field가 스키마에 속한다.

레코드는 하나하나의 데이터, 행을 의미한다.

PK(primary key)는 각각 레코드를 구분할 수 있는 유일한 값

id가 아닐 수도 있다. 이렇게 대답하면 안된다.

FK(foreign key) 한 테이블의 속성 중 다른 테이블의 레코드를 식별할 수 있는 키

이걸 통해 다른 테이블 간의 관계를 만들 수 있다.

## SQL (관계형 데이터 베이스를 관리한다)

명령어는 3가지로 나뉜다.

DDL : Data Definition Language  데이터 정의 

DML : Data Manipulation Language  데이터 조작

DCL : Data Control Language 데이터 제어 언어

SQLite는 파일로 관리되는 DB, 가볍기 때문에 다양하게 사용가능하고 접근제한이 약하다.

### SQL Syntax

모든 SQL문은 SELECT, INSERT, UPDATE 등의 키워드로 시작하고 하나의 statement는 세미콜론(;)으로 끝남

대소문자를 구분하지 않지만 작성을 권장한다.

### DDL

테이블 만들고 수정하고 삭제하고

### DATA TYPES 종류

NULL 정보가 없거나 알 수 없음

INTEGER  정수

REAL  실수

TEXT  문자

BLOB  binary 0과 1  boolean대신 사용

조금 더 엄격한 데이터형식이 있을 수 있다. 다양한 것이 있으므로

Type affinity 바꿔주는 방법이다.

### 제약조건

여러가지가 있다. NOT NULL, UNIQUE, PRIMARY KEY…

rowid 1부터 시작해서 증가한다.

UNIQUE : 겹치면 안된다?

NOT NULL : 없으면 안된다.

### ALTER TABLE

기존 테이블의 구조를 수정 변경한다.

runquary를 하면 바뀐다.
