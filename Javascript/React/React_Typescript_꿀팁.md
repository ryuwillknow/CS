# React + Typscript 꿀팁

<a href={’www.’ + child + ‘.com}> 변수는 이렇게 넣어준다. 

컴포넌트는 카멜케이스로 MyComponent

사용자 컴포넌트 구성 클래스와 함수 두가지 방법이 있는데 현재는 함수가 대세이다. 

클래스 컴포넌트는 Component 클래스를 상속해야한다.

<br>
props 여러방법

<Person name=’Jack’ age={22} />

<Person person={{name:’Jack’, age:32}} /> ⇒ props로 오브젝트를 보내준다. 
받을 때 {name, age} 로 받으면 편하다.

리액트의 속성은 객체여야한다. + 리액트의 속성이 변하면 재 랜더링된다.

이 속성이 유효한지 검증이 필요하다. 그래서 속성타입을 새로 만들어 넘겨줄 것을 요구한다!!! 이부분이 명확하게 이해되는 것은 아니다. 근데 그렇다고 하고 넘어가자. 반드시 객체의 형태여야한다. 이 검증이 완료되면 render()이후 this.props로 접근 가능하다.

<br>

## 함수 컴포넌트
함수 컴포넌트 : 타입스크립트는 화살표 함수와 같은 익명함수는 export default를 붙이지 못한다. 그래서 이름을 붙인다. 

class는 extends로  상속을 받는다면

function은 import type {FC} from ‘react’ 하고 

함수에서 :는 반환하는 자료형을 알려준다. 이걸 활용해서 함수 컴포넌트를 만든다.

```tsx
function fun1() : number {
	return num1 + num2
}
// 반환 자료형을 준다

const good : type = props => {
	return props
}
// 변수의 타입을 결정한다. 이 속성을 이용해서 함수 컴포넌트를 구성한다. 
// 제네릭 함수로 인풋타입을 결정
// 클래스 컴포넌트는 상속하는 클래스의 제네릭을 이용하여 구성한다.

const good2 : Function = (something : number) : number => {
	return something
}
```

이걸 타입으로 해야한다. 타입 별칭 이런 형식  타입 설정하기 쌍점.

화살표 함수는 타입을 결정할 수 있다.

## key & children

배열 자체를 태그 안에 넣으면 작동은 잘하지만 경고 메세지를 보낸다. 이를 해결하기 위해  map함수를 사용한다. map은 두번째 인자로 index를 받는다. 이걸 key에 넣어DOM으로 바꿔준다.

부모가 re-render되면 자식도 re-render되는 것이 비효율적이다. 이걸 막기위해 memo 사용하기도 한다.

children는  닫는 태그 없는 하나의 태그에서만 적용가능하다. 기존의 있는 태그만 하지만 진짜 p태그처럼 사용하고 싶을 수도 있으니까 children이라고 하는게 좋다.

굉장히 엄격한 언어다 타입속에 값까지 같아야한다. 실행은 된다.

콘솔로그 다찍자

일단 기본문법 {변수} 이건 {’변수’ : 변수} 라는 뜻이다. 리스트로 선언이 가능하다.

ReactNode 이 친구는 type이다!!

JSX {…props} 구문

함수 컴포넌트, 클래스 컴포넌트 이 두 가지는 props의 자유도가 있다. 아무거나 다 들어간다. 하지만 일반 HTMLElement는 들어갈 수 있는 props는 정해져 있고 구문만 들어갈 수 있다.  그래서 두개를 맞춰서 쓰는 것이 중요하다. 

리액트 17버전은 children 속성이 FC타입에 포함되어있지만 이후는 아니다. PropsWithChildren이라는 제네릭타입을 활용해서 children?:ReactNode 부분을 대체할 수 있다.  PropsWithChildren은 children 속성을 제공한다.

## ETC

styled component 사용하면 scoped css 쉽게 사용가능하다. 

`npm install styled-components`

label 안에 button 진짜 안 먹힘

styled component는 대문자로 시작해야한다.

UseEffect 에서 []를 쓰나 안 쓰나에 따라 다르다. 반드시 써야한다.

useRef 렌더링시 초기화되지 않는다. 

ref인 DOM을 선택할 수 있다.
