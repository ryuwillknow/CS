# Vue Component

data in components 정적 웹페이지가 아닌 동적 웹페이지

static이다! 

components 를 상속해야한다. 

부모가 자식에게 주는 것을 props라고 한다. 자식이 부모에게 주는 것을 emit이라고 한다.

부모가 자식에게 던지면 props로 받는다. 

부모가 자식에게 전달하는 방식을 pass props라고 한다.

validator function (value)

props 는 자식이 갖고 있는다. + 

```jsx
props = {
	msg : String
} //String으로 써야지 받아진다. 그냥 '' 하면 받아지지 않는다.
```

props 특징 :  - 없어지고 camel case가 된다.  부모에서 static-go  ⇒ props에서 staticGo로 받는다.

kebab 으로 보내고 camel로 받는다.

dynamic props 변수를 props로 전달할 수 있다!

```jsx
<MyConponent :dynamic-props="dynamicProps"/>
// 변수는 데이터에 만들어준다.
// 전자의 이름으로 후자를 보낸다.
<Example :a-b="123" static="123">
// aB에 오류가 발행한다. 숫자를 넣이 때문에  :a-b="'123'"이라 하면 오류가 없어진다.

// 
data : function () {
	return {
		dynamicProps:'12431234'
	}
}
```

컴포넌트에서 테이터는 함수여야한다. 다같이 쓰므로 → return으로

자동형변환이 되긴하는데 추천 x

## Emit

이벤트를 발생시켜야함. 어떤 이벤트가 발생하면 부모에게 전달해줘

```jsx
$emit으로 쓴다. 

// child
methods: {
    childToParent: function () {
      this.$emit('child-to-parent')
    }
  } // child에서 이벤트를 발생시킨다.

// parent
methods: {
    parentGetEvent
  }
```

오류가 뜨네요 

### Lifecycle Hooks

탄생, 마운트, 업데이트, 파괴

처음에 만들어지면 한번씩 실행

업데이트 되면 실행

create : 데이터 만들고 ( app 만들고 ) data나 computed가 이때 된다.

mount : 데이터 장착 (장착)

update: 작용한다.

내장함수? - methods, data, name과 같은 서열

타이밍 잘 봅시다.

created 일때는 데이터를 준비한다. 불러와지지않는다. queryselector - mounted()에서 합니다!

before도 있다!!!!

[230503 Vue Component](https://www.notion.so/230503-Vue-Component-28ba8c76a5bc4bee91b671450567c797?pvs=21)
