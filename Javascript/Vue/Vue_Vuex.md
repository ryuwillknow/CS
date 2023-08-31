## 1. 상태관리

state는 변수로 관리 하는 것 상태를 보여준다.

여러개의  component를 같은 data를 사용하게 하기 위해

props emit으로 관리하던 것을 중앙에서 해준다.

중앙 저장소에 데이터를 모아 상태 관리

비동기 처리는 어떻게 해야하는가???

vue add vuex 를 하면 src안에 store가 생긴다. 그 속에는 index.js

state = data

computed = getters

methods = mutations, actions

중앙 저장소가 있으면 개별 component는 data를 만들 수 있다.

중앙 저장소의 data는 $store.state

mutation은 동기식 ⇒ state를 바꾸는 것은 mutation에서 한다. 유일한 방법  handler함수는 반드시 동기적이어야한다. 비동기 사용시 state의 변화를 특정할 수 없다. state는 비동기로 쓰지 말라!!!!!

보통 대문자로 사용한다. 첫 인자는 state

commit()을 사용해서 mutation을 호출한다.

actions은 비동기 가능

context를 객체 인자로 받으며 state하지마!

dispatch()를 통해 action을 가져온다.

getters의 값이 캐시 cache 된다.

개발자 도구에서 vuex볼 수 있고 vue 볼수 있다. 분리되어있다.

action의 두번째 인자를 payload라고 한다. 첫 인자는 context

state = data

getters = state를 기본인자로 받는 함수이다. return값을 미리 계산한다. 두번째 인자로 getter를 받을 수 있다.  호출은 $store.getters.thing → computed

action, mutation에서 action이 비동기 작업을 포함한다.
