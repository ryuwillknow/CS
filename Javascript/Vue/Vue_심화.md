# Vue 문법씸화

렌더링된 DOM을 Vue instance의 data에 선언한다.(이 과정을 바인딩)

```jsx
const app = new Vue({
	el:'#app',
	data:{
		rawHTML: '어쩌구 저쩌구',
	}
}) // {} 안에 옵션을 넣는다.
```

el : 선택자

태그를 넣고 싶다면 v-html 사용  directive 라고 한다. v-접두사

v-on:submit.prevent=”onSubmit”

v-on = eventListener

submit 이 실행되면

prevent를 실행한다.

raw-html은 보안상 절 대 쓰지 않는다.

v-show element를 보여줄 것인가 결정하는 것  true false

v-if  true false  예는 아예 삭제시킨다. 에너지가 많이 든다. 애초에 없으면 많이 들지 않는다. 장단점

v-for .. in   index 순서 조심하자. 반드시 key 속성을 작성해야한다. key는 중복되면 안된다.

v-on add eventlistener 이다!!!  v-on:keyup.enter enter를 눌렀다가 올린다. 

@ 골뱅이로 숏컷이 가능하다  축약 많이 한다. 

값을 넘겨줄 수 있다. 

v-bind:href=’url’  html 기본 속성에 Vue 연결

v-bind:class

바인딩 :  이거 꼭해야한다.  

v bind는 생략해서 : 로 가능

CSS도 가능하다.

v-model은 양방향이다. v-on:input 보다 간결하다. v-on은 한방향이다.

v-model은 두 방향이다. 

## computed 보스다!!!

Vue instance가 가진 option 중에 하나다

계산 저장 재활용

methods 호출 될 떄마다 함수를 실행

같은 결과여도 매번 새롭게 계산

computed 함수의 종속대상의 변화에 따라 계산 여부 결정됨

종속 대상이 변하지 않으면 항상 저장된 값을 반환한다.

computed 함수이다!

watch 는 데이터 변화 정의

네임이 바뀔 떄마다 method의 함수를 실행할 수 있다. 단 여기서 string이어야한다.

filter는 뭔데

v-for v-if 절대 함께 쓰지말자.

Vue 스타일 가이드  v2  하지말라는 것도 있다.

handler와 deep

toggle이 무엇인가

오늘까지 CDN을 가져온다.

return this.nums.filter(a=>a%2)

@v-on 에는 반드시 함수가 들어가야한다.
