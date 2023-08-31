# CSS

CSS는 모든 것이 네모다. 모든 것이 박스다

위에서 아래로 왼쪽에서 오른쪽으로 쌓인다. = normal flow

div - 박스

각각의 박스는 4가지 영역으로 나뉘어 있다.

content padding border margin

content : 이미지 채워지는 영역

padding : 내부 여백

border : 테두리

margin : 테부리 바깥의 

```css
.margin{
	margin-top: 10px;	
}
.margin-padding{
	margin: 10px;
	padding: 30px;
}  # 상하좌우 전부 적용
.border{
	border-style: dashed;
	border-colot: black;
}
.margin-1{
	margin: 10px 20px; # 위아래 10 좌우 20
	margin: 10px 20px 30px; # 위 10 좌우 20 아래 30
	margin: 10px 20px 30px 40px; # 상 우 하 좌

.border{
	border: 2px dashed black;
}
```

width = content 영역만 해당한다

box sizeing을 border box로 하면 전체 다된다. 

F12하고 더블클릭하면 바꾸기 가능하다.

class 2개 class=”hi bye”   hi클래스 bye클래스

div.content 하면 <div class=”content”>

div#over하면 <div id=”over”>

*5도 가능하다  5개 더만들기

div.my-content>p#test*5

emmet 많이 사용해보자. Lorem   lorem100(100단어)

## CSS display

table, block, inline 등등 새로 선언해도 된다.  대신  

디스플레이에 따라 크기와 배치가 달라진다

CSS는 인라인 블록 요소로 나뉜다.

div는 블록이다. 한줄 전체를 차지한다 div

블록 요소는 마진 탑 바텀을 지정할 수 있다.

인라인은 content만큼만 차지한다.   span

블록안에 인라인을 넣을 수 있다.  diplay:block  줄바꿈이 일어난다.

display:inline content만큼만 가로폭을 차지하기 떄문에 width height margintop marginbottom 을 지정할 수 없다.

상하여백은 line-height로 지정한다. 

display에 inline - block이 있다.

display none도 있다. 공간을 부여하지 않는다.

visibility hidden하면 공간 차지하지만 보이지않는다. 

## CSS position

문서에서 해당요소의 위치를 잡아준다.

어디를 기준으로 배치시키는가가 중요하다. 

relative :  기존자리에 공백이 있다.

absolute:  기존자리가 없어짐 ,  static이 아닌 가장 가까이 있는 부모, 없으면 body를 기준으로 움직인다.

sticky : 정지한다. 스크롤을 내려도  어떤 포인트에 닿으면 계속 있는다.

fixed : viewport를 기준으로 이동한다. (브라우저의 크기에 따라 변한다)

static 모든 태그의 기본값 

alt 클릭하면 커서를 복사할 수 있다!!!! 꿀팁꿀팁

text-align :  좌우만 가운데로 만든다.

vertical align

내가 만드는 요소가 인라인인지 블록인지 확인하는 법

margin  100과 50 이 만나면 100이 된다 150 아니다

margin collapse현상이다.

위에있는 애가 없으면 margin top 은 적용이되지 않는다. 그래서 한쪽방향으로만 마진을 준다.

이미지는 마진을 먹는다.
