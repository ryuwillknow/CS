# REDUX

### flux패턴

![image (3).png](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/b6759709-02c8-4ed4-a263-d98630ec4df4/image_(3).png)

[https://velog.io/@andy0011/Flux-패턴이란](https://velog.io/@andy0011/Flux-%ED%8C%A8%ED%84%B4%EC%9D%B4%EB%9E%80)

[https://velog.io/@chaerin00/Redux-사용법-기초-useState처럼-사용하기](https://velog.io/@chaerin00/Redux-%EC%82%AC%EC%9A%A9%EB%B2%95-%EA%B8%B0%EC%B4%88-useState%EC%B2%98%EB%9F%BC-%EC%82%AC%EC%9A%A9%ED%95%98%EA%B8%B0)

[https://velog.io/@whljm1003/redux-toolkit리덕스-툴킷-사용법](https://velog.io/@whljm1003/redux-toolkit%EB%A6%AC%EB%8D%95%EC%8A%A4-%ED%88%B4%ED%82%B7-%EC%82%AC%EC%9A%A9%EB%B2%95)

### 기초 문법

```jsx
a = {abc : 11234}
b = {...a} // 복사 
c = {...a, abc : 12345} // 덮어 씌우기
```

보일러 플레이트 : 별다른 수정없이 반복되서 사용되는 코드

리덕스 안에 state를 담는다. 

react-redux, redux 차이가 있다. redux는 react만을 위한 것이 아니다. 이 사용을 돕기 위해 react-redux도 함께 받아야한다. 

dispatch 안에 action 생성 함수를 넣어준다. 이 생성된 액션 함수는 reducer 안에 들어간다. 

전달할 때 함수로 전달하기!!!

### 리덕스 사용

로그인 여부
프로필 배경
프로필 캐릭터
닉네임
=> navbar 상태관리

토글
알림

redux는 새로고침하면 없어진다.

redux-persist

combinereducers

redux-thunk  ⇒ 나중에 사용하려고 딜레이 등에 사용

https://lovecode.tistory.com/144

리덕스 정리

https://react.vlpt.us/redux/09-connect.html

SSE 기술 정리!!!

https://velog.io/@max9106/Spring-SSE-Server-Sent-Events%EB%A5%BC-%EC%9D%B4%EC%9A%A9%ED%95%9C-%EC%8B%A4%EC%8B%9C%EA%B0%84-%EC%95%8C%EB%A6%BC

https://hamait.tistory.com/792

리스트는 concat으로 한다!!! 새배열을 만들어주는 것

[https://velog.io/@s_yeah/redux-persist와-persistor.purge로-로그아웃-구현하기-redux-toolkit](https://velog.io/@s_yeah/redux-persist%EC%99%80-persistor.purge%EB%A1%9C-%EB%A1%9C%EA%B7%B8%EC%95%84%EC%9B%83-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0-redux-toolkit)

리덕스와 로그인 로그아웃

두가지 문제  persist와 여러개 reducer사용

whitelist와 blacklist 어떻게 봐야하는가?

https://chuun92.tistory.com/30  이사람이 찐다.
