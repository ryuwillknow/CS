# EVENT

이벤트 속성 이해하기

리액트코어 컴포넌트는 카멜 표기법

type 이벤트 이름

isTrusted 이벤트가 브라우저에서 발생한 것이면 true 프로그래밍으로 발생 false

target 이벤트 처음 발생한 HTML

currentTarget 이벤트 현재대상 버블링중 현재 위치한 객체 - 자기가 발생시켰으면 null

bubbles 버블링이 될지 여부 결정

getElementById?. 없으면 null반환해준다. 

버블링이란 부모에게 가는 것 window까지!!!! 이해됨

상속  최상위  EventTarget, Node, Element, HTMLElement  이 순서다. EventTarget은 addEventListener removeEventListener, dispatchEvent 세가지 메서드 3개를 갖는다. 

document 범위를 잘생각하자. window면 전체일듯?

이벤트 설정법이 여러개 있다. 일단 document.getElementById 로 가져온 DOM에 addeventlistener을 하던가 click함수를 설정하는 것이있다. addeventlistener는 여러개 가능 click은 한개만 가능 가장 밑에거.

dispatchEvent( new Event(’click’, {bubble : true}))  이벤트를 발생시켜준다. 이건 .click()과 같다.

이건 중요한것은 isTrusted속성이 false로 설정된다.

bubble을 멈추고 싶으면 SyntheicEvent의 부모인 BaseSyntheicEvent 타입이 제공하는 stopPropagation메서드를 사용하자. 이 메서드는 가까운 부모에서 먼 부모 쪽으로 이벤트가 버블링되는 것을 멈춤. 이를 이벤트 캡처링이라고 한다. 

<input> 요소의 이벤트 처리는 onChange로 처리한다. 이 친구는 ChangeEvent<T>를 가져와서 한다. 이친구는 SyntheticEvent에 EventTarget을 추가한 것이다. 여기서 타입변수는 DOM 타입이어야한다. Element이다!

OnChange 는 e.target.value e.target.checked e.target.files 형태로 얻는다.

SyntheticEvent, ChangeEvent<HTMLInputElement> 이 두개가 핵심이다.

DragDrop 컴포넌트 구현하기

drag 이벤트 : dragenter, dragstart, drag, dragover(적합한 대상위를 지나갈 때), dragleave, dragend, drop

dataTransfer는 파일드롭과 관련있다.
