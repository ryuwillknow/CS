#HTML과 CSS

HTML CSS에 대해서 알아보자

링크를 통해서 여러 웹페이지를 연결한다.  링크가 중요하다.

하이퍼 링크 = 하이퍼 텍스트

## markup language

태그를 통해서 <h> <a> 등등

- HTML은 웹페이지를 구조화하기위한 markup 언어다
- HTML은 닫는 태그가 있다.  ( 태그가 다양하다.)

MDN은 성경이다  ( 모르면 가서 읽어본다 )

W3Schools 자습서 

## 기본구조 : html 안에 head와 body태그가 있다.

html  문서의 최상위 요소

head :문서의 메타데이터 요소, 문서의 제목,  스타일, 외부파일 로딩

<title> <link> <style>  - head날리면 보인다

body :실제 구현내용

html 은 태그 안의 요소

내용이 없는 태그들도 있다

<hr> <\hr> 이렇게 쓰는게 아니라 <hr\>로 줄이기도 한다.

요소는 중첩 될 수 있음 - 태그 안에 태그 가능하다

웹은 무조건 실행된다. 닫는 태그를 안쓰면 깨진다. 등등

속성 = 태그 안쪽에 여러가지 옵션을 넣어준다.

<a href=”https://google.com”></a>   : <a>태그 내에서 href속성을 속성값으로 바꾼다. 공백이 없이?

html 의 주석은 <!— 주석 —>

<h1> 큰제목

<h2> 작은 제목

웹은 들여쓰기 2칸이다

live server를 사용하면 바로 바로 사용할 수 있다. 

그룹컨텐츠, form(장고에서 나온다)

input으로 여러가지 편의 성을 제공가능  작은 상자를 다른 부분 선택해도 가능하게

대신 id속성이 같아야 한다.

이쁘게 하는 건 css가 한다!!!!

html로 마크업 해봐라

radio버튼에 name이 중이다.

## CSS

선택하고 스타일을 지정한다.!!! h1이 선택자이다. h1을 이렇게 한다!!!

```css
h1{
  color:blue;
	font-size:15px;
}
```

### CSS 정의법

인라인, 내부참조, 외부참조

인라인 : 태그 안에

내부참조 : 헤드 태그 안쪽 <style>태그 안에 한다.

외부참조 : 헤드 안쪽에 링크 태그로 스타일한다.

묶어주는게 css? 

## F12

너무 신기하다 왼쪽위 누르고 마우스 포인터를 대면 이부분 보여준다

## 선택자

기본 선택자

전체선택자(*) 요소 (tag)

클래스 선택자는 .

아이디 선택자는 #

```css
<style>
	.green{
		color: green;
	}
	#purple{
		color: purple;
	}

id가 purple인 곳에 purple   id="purple"
class가 green인 곳에 green  class="green"
```

id와 class의 차이는 class는 여러개 id는 딱하나 찍을 때

우선순위는 id가 크다

우선순위

인라인 > id > class, 속성 > 요소

똑같으면 나중에 나온  것이 먼저다!!

html을 모양잡는데 사용하지 말고 css로 하자!

important는 주의 해야한다.

## CSS상속

안쪽이 자식요소다. 닫히기 전에  상속한다.?? 아니다. 아래에 있으면 상속된다.

단 상속이 안되는 것이 있다. 

```css
<style>
	p {
		coloer: red;
		border: 1px solid black;
	}

	span {
		border: 1px solid blue;
	}
</style>
```

```html
<body>
	<p>안녕하세요<span>김싸피</span>입니다.</p>
</body>
```

자식 결합에 대해서???   자식결합자, 자손결합자.

.box > p    box의 자식중 p태그인 것

.box p     box 아래의 모두 p태그에 다 적용

## 더보기

emmet  태그 사용하는 코딩을 단축하는 것   vsc는 내장

vsc코드에서 빈 html !하고 tap하면 바로 나온다.

거기에 자동저장 < 안쓰고 바로 ㅋㅋ

span 무의미다 여기서 클래스 스타일 등을 가져온다 - 하지만 css내부에서 해서 클래스로 가져오는 것을 추천한다.

div도 span과 비슷하다  div는 블록요소다 span은 인라인 요소다.

<b> 볼드  근데 사용하지 말자 <strong> 이 맞긴하고 나중에 꾸미자

<p> 문단

input type=’submit’ 이게 form 안에 입력된 정보를 보낸다.
