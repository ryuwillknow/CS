# HOOK

리액트에서는 className htmlFor 사용해야한다. label의 for

리액트 훅과 커스텀 훅

훅은 state와 생명주기를 연결해주는 기능을 한다.

@import @media는 앳규칙이라고 한다. 다른 css파일을 사용하고 싶을 떄 사용한다. 

index.css는 전체다. 

className을 추가하기 어려울 수도 있다. 이걸 위해서 DetailedHTMLProps와 HTMLAttributes타입이 있다. 

리액트는 use라는 접두사가 이름에 들어가는 일련의 함수다. 리액트 훅 함수는 반드시 함수 컴포넌트에서만 사용해야한다. 

클래스 컴포넌트는 직관적이지 않고 생명주기 매서드가 많아 의미와 정확한 구현방법을 알기 어렵다.this.props this.state 헷갈리다. 

훅사용법은  훅함수<값의 타입>(값) 으로 ㅅ느다. 유니온 사용가능, null 넣을때  매개변수가 2개인 함수들(useMemo, useCallback, useReducer, useEffect, useLayoutEffect)는 훅함수<값의 타입> (콜백함수, 의존성 목록)을 쓴다. 의존성 목록은 콜백함수에서 사용되는 변수나 함수의 값이 일정하지 않고 수시로 변할 수 있을 때 해당 변수나 함수를 아이템으로 갖는 배열을 의미한다.

ex ) useEffect( () ⇒ {}, [])
