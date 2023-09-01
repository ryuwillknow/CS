## MySQL 데이터 형식

**정수형**

`TINYINT`  -128 ~ 127

`SMALLINT` -32768 ~ 32767

`INT` -21억 ~ 21억

`BIGINT` -900경 ~ 900경

`UNSIGNED` 는 0부터 시작하게 해준다. `TINYINT` 인데 0부터 255까지 가능

postgreSQL 은 `check (field ≥ 0 )` 이 있다

**문자형**

`CHAR` 글자수 고정. 검색 속도가 빠르다. 최대 255자

`VARCHAR` 글자수 변동돼서 용량에 이득이 있지만 검색 속도가 느리다. 최대 16383자

앞부분에 0이 들어가는 수는 정수형에서 없어지기 때문에 문자형으로 저장해야한다. 

크다 작다, 연산 필요하다 ⇒ 정수형으로 

**대량의 데이터 저장**

`TEXT` 65535자까지

`LONGTEXT` 4294967295자까지, 4GB까지

`BLOB` 이미지, 파일, 영상을 저장하는 자료형, BLINARY LONG OBJECT

`LONGBLOB` 4GB까지

**실수형**

`FLOAT` 7자리까지

`DOUBLE` 15자리까지

**날짜형**

`DATE` : YYYY-MM-DD

`TIME` : HH:MM:SS

`DATETIME` : YYYY-MM-DD HH:MM:SS

**데이터 형변환**

`CAST`

`CONVERT`

`CONCAT` 문자열을 이어주는 함수

`SELECT “100” +”200”` 은 300이다. 그래서 `CONCAT` 을 써야한다.
