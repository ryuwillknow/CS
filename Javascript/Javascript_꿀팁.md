함수 선언식 표현식

여러 방법

this

호출은 window  ⇒는 호출이아니라 상위로 된다.

중요한 것은 object안에 있는 method이다!

객체를 가리킨다!!! this 단 for each에서는 조심해야한다. 콜백함수에서 조심?

아니다!!!!! 그냥 해도 되는데 for each 만 다른 느낌이다.

호이스팅  var

선언식 호이스팅 o

```jsx
function add() {
	// do something
}
```

표현식 호이스팅 x

```jsx
const sub = function(num) {
	return num
}
```

화살표 함수

```jsx
const arrow = name => name * 2
const arrow = () => this.state * 2
const arrow = () => ({'a' : 'b'}) // object를 return없이 
```

콜백함수 : 개념이 다른가?

배열 메서드

filter : return이 true인 것들만 새로운 배열

map : return한 값들로 새로운 배열

reduce : 첫인자는 변수로 받는다 변수와 배열의 모든 것들의 관계

Array(45).fill(1).map((x, y)⇒ x+y)      //두번째인자는 현재의 index

array.sort(()⇒Math.random - 0.5)  shuffle // 이거 메커니즘이 독특하다.

인터프리터 언어인데 어떻게 호이스팅이 가능한가? -> 해석할 때 최상단으로 이동한다.

영어 길게 말하기

데이터 베이스를 어떻게 객체로?? ⇒ 싱글톤 관련

localStorage, cookie, session, 차이와 용도

다 객체인가? 쓰레드도 객체로 만들 수 있고 

spa ssr router   DRF RESTFUL  라우터와 

```jsx
<router-view/>
```

lifecycle hook 에 대해서  

native는 뭔데

환경변수설정!!!

vue에서 .env.local에서 local은 모드 이름이다

기본적으로 development, test, production 세가지가 있다. 이외의 다른 모드를 사용하면 다음 명령어를 사용한다.

npm run serve — —mode local    여기서 이름은 자유자재로
