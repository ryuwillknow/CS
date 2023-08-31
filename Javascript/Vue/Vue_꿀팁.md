# 종합꿀팁

formData()

VUE는 프레임워크이다

REACT는 라이브러리

JS의 in은 다르다!!!!  index만 말한다. 혹은 key값만 말한다.

python처럼 하려면 includes를 사용해야한다.

on off는 토글을 활용하자.

대문자 조심하자

classList는 array가 아니다. array like object이다.

대신 toggle을 사용하자.

v-on 함수 실행시 인자가 없으면 event그대로 아니면 

스타일은 array안에 딕셔너리 형태로 내부에 적용한다.

```jsx
<div :style="[a, b, c]"></div>
<div :style="a"></div>

// a= {
	so : so,
	low:low
}
```

npm install bootstrap@5.2.3   이렇게  다운 받을 수 잇다.

어디까지 바로 업데이트가 되는가   for는 바로 업데이트가 된다. data의 길이 개수 변화? 이벤트 마다?

main.js에서 설정해준다. import bootstrap

for문을 실시간 반영하려면 반드시 array여야한다. array안에 object이게 모두 

npn install 후에 npm run serve

```jsx
const { defineConfig } = require('@vue/cli-service')
module.exports = defineConfig({
  transpileDependencies: true,
  lintOnSave:false
})
```

### Vue Cli

run serve하는 위치가 중요하다.

v-model 은 data에서 ‘’을 받자? props가 string을 받는다.

array를 바꿀 때는 $set을 사용해야한다!!!!!!!!!!!!!!!!!!

style은 전체 의존성!!!!!

v-on click native!!!!!!!!!!!!!!!!!!
