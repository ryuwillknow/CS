## 프로젝트 내부 구조

node_modules 는 python의 venv 같다. 의존성 모듈이다. gitignore에 이름이 있어 push하지 말자.

자바스크립트의 파편화 표준화경향이 있다. ⇒ 자바스크립트는 버전마다 조금씩 다르다. 

이걸 맞춰주는 것이 node_modules의 Babel이다!!! 번역해준다. 과거버전으로 바꿔준다.

파편화 개념 유념하자.

Webpack : 모듈간의 의존성문제를 해결하기 위한 도구 - 의존성이란?

의존성이 뭔소리여

모듈수가 많아지고 의존성이 깊어지면 발생한 문제가 어떤 모듈간의 문제인지 파악하기 어려움

Vue도 app이 있고 트리구조이다.

component는 조각들 nav 

Component based architecture 특징은

관리, 재사용성, 확장가능, 캡슐화, 독립적

결국

.Vue를 하나 만들어서 이게 하나의 component이다.

### 실전

src안에 component를 주의하자

component 안에 vue를 만든다. 이때 template안에 root를 만든다. 이때 root는 반드시 하나여야한다.

만들고 APP.vue의 script에 **불러오고 등록하고**

위에 template에 쓴다.

Vue에서 .은 현재파일 @은 src폴더이다!

vue 자동완성은 vue tab

CSS파일은

SFC

**script scoped   그곳에서만 적용된다. scoped지우면 상속된다.**

props로 변수 할 수 있다.
