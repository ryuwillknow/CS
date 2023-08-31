# Vue Life Cycle Hook

vue navigation guard

3종류가 잇다 전역 라우터 컴포넌트

1. Global Before Guard ⇒ beforeEach사용

to  어디로 간다

from  현재

next 이동하기 위해 호출해야하는 함수

화면이 전한되기 전에 router.beforeEach()가 호출되는데 이걸 대기상태로 만들고 next()를 호출해야한다.

2번 나오는 이유

모든페이지에서 beforeEach가 실행된다.. 

next() 한번만 써야한다!

전역처리도 가능하다! ⇒ !사용

1. 라우터 가드

beforEnter 사용 to from next

위치도 다르다

router내부에 beforeEnter을 사용해서 path name component beforeEnter

1. 컴포넌트 가드

Params 변화감지

컴포넌트가 재사용되었기 때문

lifecyclehook이 실행이 안되었기 때문

얘는 view.vue에 한다.  name, data 다음에

찾을때 순서대로 찾는데 가장 밑에 path:’*’ 하면 남은 곳은 모두 redirect로 간다.

반드시 가장 밑에 있어야한다!!!

++++

404 Not Found 뜻은 없는 페이지!

만약에 형식이 유효하지만 찾을 수 없는경우

```jsx
// 이미지가 없으면!
<p v-if='!imgSrc'></p>

// ‘/dog/:breed' 에서 뒤가 잘못되었다면?
// catch로 받는다.
this.$route.push('/404') // 로 보낼 수도 있다.
```

? = optional chaning  변수가 있을 때만 출력

es2020에 추가됨

코드 타이밍이 안맞을 수 잇다. ?넣는 이유. 없으면 오류가 난다. 

에러 안내고 아무것도 안뜨는 것 방지

pk 자체적으로 처리하는 것이 맞는가? ⇒  아니다!!!
