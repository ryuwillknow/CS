# JAVASCRIPT

위에 채워넣기

## DOM

javascript는 웹페이징서 다양한 기능을 구현하는 스크립트 언어이다.

### Browser APIs

여러가지 기능이 있다. 오디오, 목소리 등등 다양한 기능이 있다.

이 중에 DOM이 있다.

DOM : Documet Object Model

HTML/CSS를 조작할 수 있다.

### Node

DOM의 구성요소중 하나이다.  

DOM의 주요객체는 window, document이다. 추가 공부 navigator, location, history, screen 등

window 객체!! - 브라우저 창 느낌 window.alert해봐!

document 하면 html문서가 나온다!  head는 표시안되지만 중요한 데이터

window.document이다! window 생략 가능

document.title   

태그 = Node다!!  속성이 class 등등

선택 메서드

document.querySelector(selector) - 일치하는 element 한 개 선택

document.querySelectorAll(selector) - 여러 element 선택

일반적으로 forEach 쓴다.

querySelectorAll()에 의해 반환되는 NodeList는 DOM의 변경사항을 실시간으로 반영하지 않는다.

조작 메서드

document.createElement  node.innerText  node.appendChild(부모요소에 넣기 ) 조작 가능하다.

node.appendChild → 만약 html에 존재한다면 복사가 아닌 이동이 된다.

htmlcontent.innerText

```jsx
ptag.style.visibility = 'hidden'
'hidden'
console.log(ptag.innerText)
console.log(ptag.textContent)
VM549:1 
VM549:2 querySelector

const h1 = document.querySelector('h1')
undefined
console.log(h1.classList)
VM849:1 DOMTokenList ['red', value: 'red']
undefined
h1.classList.remove('red')
undefined
h1.classList.add('red')
undefined
h1.classList.toggle('blue')
true
h1.classList.toggle('blue')
false
```

toggle은 무엇인가 클래스가 존재한다변 제거하고 false반환 존재하지 않으면 클래스 추가하고 true 반환

script태그 안에 코드 넣는 것과 같다.ㅇㅇㅇㅇㅇㅇ

```jsx
<script>
    //
    const mango = document.createElement('li')
    mango.innerText = '망고'

    const parent = document.querySelector('#list')
    parent.appendChild(mango)

    const pineapple = document.createElement('li')
    pineapple.innerText = '파인애플'

    parent.prepend(pineapple) // 위에 추가하기

		const kiwi = document.createElement('li')
    kiwi.innerText = '키위'

    const banana = document.querySelector('#banana')

    parent.insertBefore(kiwi, banana) // 바나나 위에 추가하기

  </script>
```

append(), prepend(), appendTo(), prependTo(), after(), before()

insertBefore() insertAfter()

### 예습

addEventListener(’click’, () ⇒ {

changeFont()

})

function changeFont() {

const LiTags = document.querySelectorll(’li’)

식별자 const function let 등등

let이 변화 가능하다.

const 재선언 불가능

원시 자료 vs 참조자료

참조자료 Object(key, value)와 Array(순서), function

object 내부는 .과 []로 접근이 가능하다.

array는 .length 접근가능

함수 두 종류 + return은 너 마음대로

```jsx

function add(a, b) {
	//say somethiing 선언식 호이스팅 발생
}

const add2 = function (a,b ) {
	//say something 표현식 호이스팅 안됨
}
```

익명 함수 쓰면 바로 실행?? for문 등 제어문 내부에서 function바로 쓰기…

이건 콜백함수이다!!!!

```jsx
colors.forEach(function (color) {
	//do
}

colors.forEach((color) => {
	return // something
}
```

… 잘 사용하자

if else if else

while

for in (Object 속성 순회 KEY값)

for of (Array 속성 순회)

array.foreach

인자 개수 상관 없다. … 잘 사용하자

array매서드 여러개 잇다.

array  .foreach .map(각요소에 실행하고 새로운 리스트 반환) .filter(True인 것들 반환) .find(True인 첫번째)  some every  1개라도 모두

객체 선언 function으로 한다.

```jsx
funtion Memver(name, age, id) {
 this.name = name
 this.age = age
 this.id = id
}

const memver3 = new Member('isac',21,12323)
```

## Dom

window - tap 포함 Object

document - 웹페이지 Object

```jsx
<script src='something.js'> </script>
{% load static %}
<link rel="stylesheet" href="{% static 'dark.css' %}">
```

static link가!!!! 반드시 부트스트랩 다음에 있어야한다.

+++ css는 캐시에 저장된다. 반드시 수정시 ?after를 붙여줘야한다.

z-flex
