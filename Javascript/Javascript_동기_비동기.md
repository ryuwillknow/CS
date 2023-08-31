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

callback은 어제 배웠대…
