# layout

## float

normal flow 를 벗어난다.

float : none이 기본값 left, right를 주면 inline요소처럼 쓸 수 있다.

단 다 띄워야한다. inline안에서는 적용이 되지만 블록끼리는 겹치게 된다. 

겹치는 것을 clear both를 주면 잘 붙는다.

옆으로 붙이려면 float  밑으로 붙이려면 clear both

더 좋은 녀석이 있다.

flexbox  grid 

## Flexbox

컨테이너를 두고 안쪽에 아이템들을 넣자

display: flex;

인라인 flex를 하거나 display:flex하면 시작이다

flexbox는 박스 안에 맞게 배치해준다.

flex 속성과 item 속성으로 나뉜다.

## Flex 속성

direction, wrap 배치

공간 나누기 justify - 메인축  align 교차축

공간을 배분한다. 마진으로 조절하는 것이 아니다.

flex하는 순간 높이가 맞는다. container의 높이

space between space around

align - 은 기본이 stretch

center 감사합니다.

baseline 은 글 쓰는 선이다. p, g는 넘어가는 그 선

flex direction 방향축을 바꾼다. main axis는 기본적으로 row이다

align은 justify 랑 똑같다.  확인하려면 여러줄이어야한다. 

grow, order 아이템 배분

grow늘어나는 비율도 조정이 가능하다. 

vw vh 비율이다. px %같이 사용한다.
