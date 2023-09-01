## 스토어 프로시저

Delimiter는 번역하면 '구분 문자 입니다. ' 일반 텍스트 또는 데이터 스트림에서 별도의 독립적 영역 사이의 경계를 지정하는 데 사용하는 하나의 문자 혹은 문자들의 배열등을 말한다고 합니다.

한 줄씩 보내는 것이 아니라 통채로 보낸다.

함수처럼 활용할 수 있다.

`DECLARE num INT;` 선언

`SET num = 200;` 초기화

`IF`

`END IF`

`END $$` 이거까지 해줘야한다.

`CALL func1()` 로 호출한다.

`CASE`

`WHEN a = 3 THEN`

이런 구문도 있다. 

`SUM(buy.price * buy.amount)` 하고 `JOIN` 하는 거 중요하다

```sql
SELECT member.mem_name, SUM(buy.price * buy.amount) "총 구매액",
	CASE
		WHEN SUM(buy.price * buy.amount) > 1500 THEN
			"VVIP"
		WHEN SUM(buy.price * buy.amount) >1000 THEN
			"VIP"
		WHEN SUM(buy.price * buy.amount) > 1 THEN
			"NORMAL"
	END "회원등급"
	FROM buy 
		JOIN member 
		ON member.mem_id = buy.mem_id
    GROUP BY member.mem_name
    ORDER BY SUM(buy.price * buy.amount) DESC;
```

쉼표의 위치 조심하자  문장 마무리만.+ 띄어쓰기는 다른 문자로 표현하겠다는 뜻

외에도 while문과 동적SQL

`PREPARED`로 준비 `EXECUTE`로 실행
