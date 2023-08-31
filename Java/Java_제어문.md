# if와 switch

switch는 값이 온다. break 나올때까지 실행한다. 

```java
switch(3) {
	case 3:
		System.out.println(4);
		break;
	case 4:
		System.out.println(5);
		break;
}

// break없으면 4 5 출력한다.
// default는 else의 역할을 하낟.
```

# 반복문

```Java
for ( 초기화식 ; 조건식 ; 증감식) {

}

while (조건식) {

}
```

do {

} while (조건식) ;  이 친구는 일단 실행하고

for else는 알아서

Scanner sc = new Scanner(System.in);  

int num = sc.nextInt()이게 입력받기다. 정수형

String str = sc.nextIine() 문자열 입력받기

**outer: continue 위치 라벨  ### 매우매우매우매우중요하다. 이중 삼중 for문에서!!! 라벨 위치까지 break는 싹 다 정지다.**
