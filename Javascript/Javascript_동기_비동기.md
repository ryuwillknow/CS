# 동기 비동기

자바는 thread객체가 있다. thread 는 OS에서 제공하는 기능이다. 

브라우저는 thread를 작동할 기능을 제공하지 않는다. js는 브라우저에서 실행

비동기를 실행하는 수단이 thread이지 둘은 관계가 없다.

과연 브라우저는 single thread일까? 

동기와 비동기 면접에 물어본다.

비동기 : 기다리지 않는다. 바로 다음거 처리 병렬처리

동기 : 일을 순서대로 처리하는 것

동기 vs 비동기는 그때 그때 다르다. 

은행 - 동기식이어야한다. 입금 송금  **순서가 중요하므로**

웹사이트 - 동영상 나중에 나온다. 기본적인 것은 먼저 나온다.

javascript는 single thread 언어이다. 여러작업을 동시에 처리하지 못한다. 

single이 더 효율적이다. 인수인계 맥락전환이 없으니까!

## JS 에서의 비동기

call stack - web API - task Queue - Event Loop

task Queue에 결과를 넣는다. call stack비어있으면 옮긴다. call stack에서 실행

무조건 보낸다. 결국 그 일이 무엇인지가 중요하다. setTimeout은 무조건 web API로 넘어간다.

비동기통신하기 위해 Axios이다!!!

비어있을때 보내는게 제일 중요하다.

깜빡하는 것을 없애기 위해서 미리 무언가가 있어야한다. 로딩중을 어떻게 구현하는가!!!!!!!!!!!!!!!

## Axios

CDN이다 가져와야한다. 

```jsx
<script>
	axios.get('요청할 URL')
	.then(성공하면 수행할 콜백함수)
	.catch(실패하면 수행할 콜백함수)

</script>
```

## AJAX가 무엇이냐

Asynchronous JavaScript And XML  화면 전체를 새로고침 하지 않아도 서버로 요청을 보내고 데이터를 받아 화면의 일부분만 업데이트 가능

비동기 통신이 없으면 스크롤이 올라간다. 새로고침이 된다.

form으로 요청을 보내면 새로고침이 된다. 그러므로 javascript가 일을 할 것이다. 

요청을 보낼 때 userpk와 csrftoken 이 필요하다. axios도 똑같다.

```html
<form id='asdf' data-user-id="{{person.pk}}">
</form>

<script>
	const form = document.querySelector('#asf')
	form.addEventListener('submit', function (event) {
    event.preventDefault()
    const userId = event.target.dataset.userId
    axios({
      method : 'POST',
      url : '/accounts/userpk/follow/',
    })
  })
</script>
```

위처럼 데이터를 태그에 넣을 수 있다.

반드시 다 소문자여야한다!!!!!!!!

좋아요 버튼 - 처음 가져올 때 리스트에 있으면 

그다음에 자바스크립트가 누르면 버튼을 바꿔준다.

비동기는 요청을 받는 동안 다른 작업을 할 수 있다.
