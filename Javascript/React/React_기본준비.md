# 0. 기본 준비

build 모드와 개발자 모드

이전에 웹팩은 모듈번들러로 여러 파일을 결합하여 더 단순한 형태로 바꿔주는 역할을 한다.

개발자모드는 npm start로 한다. 이러면 핫모듈교체를 해줘서 바로바로 적용이 가능하다.

VSC에서 프리티어 다운로드하기

테일윈드 설치하기

헤드윈드 설치하기 → 테일윈드 관련 코드를 이해하기 쉬운 순서로 재배치해 주는 프로그램

포스트CSS → 테일윈드로 인해 생기는 불필요한 경고메세지를 삭제해준다.

npm  i -g typescript ts-node를 받아야한다. → 타입스크립트 컴파일러

npx create-react-app template —typescript 가 통한다.

.prittierrc.js 사용법

```jsx
// .prittierrc.js
module.exports = {
	singleQuote : true,
	semi : false,
}

// 동작하지 않게 하기
// prettier-ignore
```

**가짜 데이터** 만들기  중요 - 외부패키지를 설치하는 방법을 알아보자

Node.js에서 외부 패키지를 설치하는 방법은 2가지가 있다. 

npm install or npm i  -S 실행에 필요한 패키지  -D 개발을 위한 패키지 설치   

package.json : dependencies 안에 설치한 패키지가 들어간다. -D만큼

자바스크립트로 개발된 패키지를 타입스크립트에서 사용하려면 @types/로 시작하는 타입라이브러리를 추가로 설치해야한다.

실제 패키지는 node_modules에 설치된다. 프로젝트 공유할 때 지워야한다. 공유받은 사람이 npm i만 치면 자동으로 다운이 된다. 

chance 가짜데이터 제공 luxon 날짜 시간을 이해하기 편한 형태로 만들어준다.

npm i chance luxon

npm i -D @type/chance @type/luxon
