# 클래스 컴포넌트  잘 안쓰긴 함


React DOM은 해당 엘리먼트와 그 자식 엘리먼트를 이전의 엘리먼트와 비교하고 DOM을 원하는 상태로 만드는데 필요한 경우에만 DOM을 업데이트합니다.

비교할 뿐이다? conponent의 코드를 전부 실행하는 것이 아니다?

매초 전체 UI를 다시 그리도록 엘리먼트를 만들었지만 React DOM은 내용이 변경된 텍스트 노드만 업데이트했습니다.

`componentDidMount()` 메서드는 컴포넌트 출력물이 DOM에 렌더링 된 후에 실행됩니다.

`componentDidMount()`는 컴포넌트가 마운트된 직후, 즉 트리에 삽입된 직후에 호출됩니다. DOM 노드가 있어야 하는 초기화 작업은 이 메서드에서 이루어지면 됩니다. 외부에서 데이터를 불러와야 한다면, 네트워크 요청을 보내기 적절한 위치입니다.

UseEffect를 이해하기위해서 이 친구는 렌더링 이후에 실행된다. 

이때 다른 데이터를 가져오거나 네트워크 요청을 보낸다.

[리액트 생명주기](https://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)

리액트는 컴포넌트 내부값과 관련있는 로직만 존재해야한다. 이외의 것은 side-effect라 칭한다.(document.title과 비동기함수 같은 것, 타이머가 안쪽에 있으면 안 될듯.  콜백함수를 실행하는 시점이 문제가 생길수도? ) 이런 친구들은 useEffect나 생명주기 함수로 관리한다. [출처](https://points.tistory.com/86)
