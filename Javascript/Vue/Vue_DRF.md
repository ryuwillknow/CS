# DRF = django_rest_framework

VUE with DRF

CORS

action은 commit 무조건은 아니다. commit은 state바꿀 때 사용

created 일때 가져와야한다. 그래서 method 만들고 created()에서 실행

```jsx
cess to XMLHttpRequest at 'http://127.0.0.1:8000//api/v1/articles/' from origin 'http://localhost:8080' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
```

CORS 마약탐지견 ⇒ 브라우저가 차단하는것

에러는 프론트엔드에서 보지만 해결은 서버에서 해줘야한다.

Cross Origin Resource Sharing

보안상의 이유로 동일출처정책(SOP)에 의해 상호작용하는 것을 제한 함

이렇게 해킹한다!!!

출처란 무엇인가?  protocol host port 가 같으면 동일 출처다!

https까지 같아야한다!

인증에 대해서

세션과 토큰을 활용한다.  DRF frame work  authentication 들어가자

권한에 대한 이야기도 있다. 

쿠키는 로컬스토리지에 넣는 건데 잘 안 쓴다. 보안 때문에

basic과 session, remote 세 가지 방법이 있다.

비연결성 

상태를 저장하지 않는다.

통행증 토큰

출입명부  세션

토큰과 세션은 중요한 정보를 누구에게 맡기냐의 차이다.

세션은 서버에 부하가 있다

토큰은 보안에 취약하다. 토큰 탈취! 무겁다. 

기기 접속제한 - 토큰으로 하기 어렵다. 시간제한 토큰 발급
