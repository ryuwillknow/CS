# Typescript

type을 선언해주자. 하지만 js와의 호환을 위해 추론을 하기도 한다.

ts-node 로 실행 가능

tsc app.ts를 하면 컴파일된다. app.js가 생긴다.

그 파일을 node app.js 하면 실행된다. 

중복된 함수 구현 오류는 tsc —init으로 해결한다.

number 타입이 있다!!!

never 타입은 절대 반환을 하지 않는 함수를 나타낸다. 따로 적지는 않는다. 

유니온 타입은 변수의 타입이 여러 개일 때 사용한다.

```tsx
let a : string | number;
```

커스텀 타입이 있다. 객체 반환과 같다.???

```tsx
type James = int;

type Student = {
	name : string,
	age : number,
	teacher : James
}

let student: Student = {
	name : "abc",
	age : 123
  teacher : 55
}
```

배열타입은 배열타입과 제네릭 배열타입 두가지로 나눈다. 

```tsx
let list: number[] = [1,2,3,4,5]
let members : string[] = ["김지구", "강석우", "임건도"]
members.push("양진호")
let everything: any[] = ["망치", 100, true, null]
let something: (string | number | boolean | null)[] = ["김김김", 100, true, null]

// 제네릭 타입

let str:Array<string> = ["와우"]
let str:Array<string | number> = ["zizizi", 1234]
let str2 : typeof str = ["bkbkbk", 4321]  // 타입을 참조할 때 타입 쿼리를 사용한다.

// 제네릭 타입은 익명함수도 받을 수 있다.
let functions : Array<() => string> = [() => "gogo", ()=> "nopnop"]
console.log(functions[0]()) // gogo
```

튜플은 

```tsx
let member:[string, number] = ["와우", 1234] // 이렇게 하면 타입을 강제한다.
개수가 더 많으면 유니온 타입이된다.
let member:[string, number] = ["와우", 1234, 12345] // 이거 패치됨 안됨
```

타입스크립트는 객체 선언할 때 어떤 타입인지 명확하게 정의해야한다.

객체 타입

```tsx
const student : object = { } ;
const student2 = {}; // any type
let student : {
	name : string,
	grade : number
}

student = {
	name : "학생",
	grade : 3
}
// same : true은 안된다.

let student2 = {}
student2 = {
    abc : "1234",
    letitgo : true
}

student2 = {
  abcddd: 1234,
  letitgo: true,
  plz : "!@#$"
}
// 막 쓸 수 있다.

let student : {
	name : string,
	grade : number,
	age?: number
}
// 이렇게 하면 선택적으로 사용가능하다.
```

인덱스 시그니처는 신기하다. key값을 지정가능하다.

```tsx
let student :  { [index: string] : number} = {}

student.id = 22000234
student.id = "asdf" // error
```

열거형 (Enums) : 상수, final의 개념  변하지 않는다. ⇒ 이건 =으로 한다!

```tsx
enum good2 {
    James = 1234,
    Paka 
}

console.log(good2.Paka) // 1235  숫자  + 1

enum good3 {
  James,
  Paka,
}

// 0, 1
```

타입 별칭(type aliases) 

```tsx
type Food = string;

type james = "james"
const name2 : james = "James"  // 오류난다.
```

인터페이스 : 객체처럼 정의한다. 타입별칭과 비슷하다.  객체, 함수 등 다양하다. 인터페이스는 readonly가 있다.  ?는 선택적

```tsx
interface User {
	name : string
	age : number
}

let user1 : User = {
	name : "daddy",
	age : 20
}

let user2 = {} as User
user2.name = "mommy"
user2.age = 22

interface Addnumber {
	(x: number, y: number) : number // 마지막은 return해주는 값의 유형
}

let addnumber : Addnumber = (x, y) => {
	return x + y
}
```

객체랑 클래스랑 거의 비슷하다…? 이런 implementㄴ로 클래스 정의할 수 있다.

```tsx
interface User {
	name : string
	age : number
	getAge(age:number):void
}
// object는 , 가 있어야한다.
let a : object = {
    a : "1234"
    b : 1234
} 

class UserFakerr implements User {
	name : string = "철수"
	age : number = 20;
	getAge(age:number) {
		console.log(this.age)
	}
	otherFun() {}
}

```

인터페이스는 한번더 선언하면 확장, type aliases는 확장 불가

extends로 확장도 가능하다.

중요! 리터럴 타입과 유니온 연사자를 활용한 타입은 확장 불가능하다

타입은  &로 확장할 수 있다.

```tsx
type User = {
	name: string
}

type UserInfo = User & {
	age: number
}
```

가급적이면 인터페이스 사용하고 유니온 튜플을 사용해야하거나 인터페이스로 표현할 수 없으면 타입별칭을 사용하자
