## JOIN 에 대해서

별거 없다. 쫄지 말자.

`SELECT * FROM table1 JOIN table2 ON table1.id = table2.id WHERE table1.id = 13`

where의 조건의 table 1을 찾고  같은 값의 table2를 모두 찾는다.

`table1.id table1.name table2.name table2.id` 로 간결하게 할 수 있다.

내부 join = 둘다 있어야한다.

외부 join = 하나만 있어도 된다. `LEFT`, `RIGHT`, `FULL` 선택해서 넣는다. 

상호 join은  모두
