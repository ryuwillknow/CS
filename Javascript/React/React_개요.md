# 리액트 개요

리액트는 클래스와 함수 두 가지 방법이 있다. → 여기서는 함수로

깃허브 타고 들어가면 README.md에 

npx create-react-app <name> 

npm start 

src 의 index.js에 적혀있는 대로 동작하는 것

app에서 css, png import해서 사용한다.

index.css도 있다. 지워야한다.

index.js의 root?

public에 index.html의 root 태그에 render하는 코드가 index.js안에 있다.

터미널에서 npm run build ⇒ build 폴더 생긴다.

파일용량 최대한 줄인다.

serve -s build 하면 build 안에 있는 index.html을 실행하자.

npx serve -s build

리액트는 사용자 정의 태그를 만드는 기능이 본질이다.

사용자 정의 태그 = 컴포넌트  함수로

리액트 속성은 props이라고 한다. 

props에 객체가 있다. 

```tsx
function Header(props) {
	return <header> <h1> 하이루 </h1> <header>
}

function App() {
	return (
		<Header title="james"> </Header>
	}
}

// props는 Object고 props.title은 "james"가된다.
// 직접 props를 다루고 싶으면 중괄호를 넣어야한다. f스트링느낌이다.
```

state 는 함수로 부모에게 접근 하지만 바뀌지 않는다. app함수는 다시 실행되지 않기 때문이다. 

```tsx
import {useState} from React
// 이 훅은 리액트에서 기본으로 제공한다.  0 번째 원소 1번쨰 원소는 함수 배열 return한다. 
```

useState가 배열을 반환하기 때문에 배열을 맞춰준다.

setMode 하면 다시 실행된다. !!! 재랜더링

문자열 조심하자. 태그의 속성은 다 문자열이 된다. 

===
