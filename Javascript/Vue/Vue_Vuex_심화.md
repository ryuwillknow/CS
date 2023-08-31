local storage - 새로고침시 안바뀜

plugins - 플러그인 설치 방법

## Local storage

상태유지 

새로고침시 초기화된다. db도 없는데 어떻게 데이터를 저장하는가

개발자 도구의 application stoage

브라우저의 내장객체

다른 탭에서도 공유

보안관련 정보는 저장하지 마라!

localStorage는 문자열만 받는다.

```jsx
const number = [1,2,3,4,5]
localStorage.setItem('numbers', numbers)
// 보내기, 문자열로 저장 약간 형변환이 일어낟나.

const input = localStorage.getItem(numbers)
console.log(input)
// 받기
// 하지만 , 문자열로 받는다.
// '1, 2, 3, 4, 5'  이건 사용할 수 없다.

const stringNumbers = Json.stringify(number) // 문자열로 변환해서 저장해야한다.
localStorage.setItem('numbers', stringNumbers)
const numbers = localStorage.getItem('numbers')
const parsedNumbers = Json.parse(numbers)
```

장바구니에 사용

vuex-persistedstate !!! 이거 영구적으로 저장해준다.

npm i vuex-persistedstate

```jsx
import createPersistedState from 'vuex-persistedstate’

...

plugins:[
    createPersistedState(),
  ], // 배열 조심하자
```

자동저장이 아니고 수동저장하려면 

로그인 로그아웃에 사용된다. ⇒ 토큰을 저장한다!

## Vuex binding helper

syntactic sugar 문법으로 간단하게 만든다.

store에서 쓰는 mutation action을 쉽게 쓰게 한다.

import 받아와야한다.

mapState 2가지 방법이 있다. 객체로 쓰는 법, 배열로 쓰는 법

배열은 그대로 쓸 때

객체는 이름 바꾸거나 추가기능 쓸 때

mapAction mapState와 같은 방식으로 사용

## Modules

모듈 파일 분리

해야할 일

mapState 

로컬 스토리지 로그인 - 캐시 무슨 차이

[로컬 스토리지 캐시 차이](https://velog.io/@yiseul/%EC%BF%A0%ED%82%A4-%EC%84%B8%EC%85%98-%EC%BA%90%EC%8B%9C-%EB%A1%9C%EC%BB%AC%EC%8A%A4%ED%86%A0%EB%A6%AC%EC%A7%80%EC%9D%98-%EC%B0%A8%EC%9D%B4)
