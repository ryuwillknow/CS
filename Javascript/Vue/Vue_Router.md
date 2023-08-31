## Router

네트워크에서 경로를 선택하는 프로세스

서버는 하나의 html만 제공한다.

화면이 변경돼도 주소의 변화는 없다.

routing이 있어야 url을 통한 페이지 변화를 감지할 수 있다.

화면이 바뀌는 것에 따라서 주소를 바꾸고 싶으면 routing을 한다.

설치시 조심해야할 것은 app.vue가 날아간다!!!!!!!!!!!!!!!!!!!!!!!!

history mode? yyyyyyyyyyyyyy

방문 기록을 활용해서 이동 기록을 남길 수 있다. 히스토리모드가 아니면 8080#index 처럼 hash mode를 써야한다.

동적 라우팅

a태그와 같다.!!!!!!!!!!!!!!!!!

SPA는 무엇인가ㅏ!!!!! 이런 개념!!! 때문에 라우터가 필요하다????

v-bind를 통한 라우팅 

```jsx
:to = "{ name: 'home'}"  //이렇게 할 수 잇따. related name과 같다!
// 이걸 router에 추가할 때 name 항목이다.

// in router

{
	path : '/hello/:userName',
	name : 'hello',
	component: HelloView,
}

//in .vue
<routerlink to="/hello/jeeho"> </routerlink>

// in hello
{{ $route.params.userName }}

// in .vue
<routerlink :to="{name:'hello', params:{userName : 'jeeho'}}"> </routerlink>

//method
this.$route.push({name:'hello'})
```

SSA는 단 하나의 html을 가져온다.

js가 내용물을 바꿔주는 것이다  이게  SSR

lazy-loading : 나중에 다운 받는다. 

source를 보면  app.js 가 있는데 about으로 이동하면 추가가된다.

source가 다운 받은 모든 것을 보여준다
