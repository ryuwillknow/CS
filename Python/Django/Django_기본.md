# django

웹 프레임워크 이해하기

어떻게 서비스를 만드는 지…

데코레이터 : 함수를 꾸며주는 함수, 함수를 감싼다

함수 안에 내가 원하는 함수를 넣는다. 

미리 구현해서 모아 놓은 것 = framework

뼈대와 규약을 가지고 무언가를 만드는 일

협업이 용이하지만

선택의 폭이 좁아지지만

러닝커브가 존재

비즈니스 로직에 집중할 수 있다.

다양한 프레임 워크가 있고 각자 규칙이 있다.

장고는 파이썬으로 작성된 프레임워크

## 클라이언트와 서버

둘다 컴퓨터다

클라이언트는 서버에게 requests를 주고 서버는 responses를 준다.

웹브라우저가 클라이언트, 서비스를 요청하는 주체

서버, 요청이 들어오면 서비스를 응답하는 주체

주소창에 치는 것은 요청하는 것이다.!! 

주소로 요청하고 html로 받는다.  웹브라우저는 요청과 해석(랜더링)을 한다. 

장고는 서버를 구현하는 웹 프레임워크

데이터베이스와 소통하고 response를 한다.

최근 영상편집, 엑셀 등 웹의 영역이 넓어지고 있다.

그래서 장고에 없는 기능이 많다. 그래서 데이터를 주고 클라이언트가 html로 만든다. 이때 사용하는 도구가 vue이다.

freeze - requirments.txt

pip install -r reuirements.txt

서버 키는 법

python [manage.py](http://manage.py) runserver

끄는 법

ctrl c

장고의 프로젝트는 하나의 서비스이다. 

앱의 이름은 복수형으로 적는 것이 관례이다.

앱은 하나의 큰 기능 단위이다. - 이건 개발자의 재량이다. 

다양한 구조가 있다.

앱을 만들면 setting.py에 반드시 추가해야한다.

장고는 크게 3가지 구조가 있다. MTV model view template

model  데이터

view 로직

template  보여지는 것 html 

URL → view → template 기초

## new

다음 과정이 서버의 역할

모든 서버는 소켓이 있어야한다.  듣는 부분이다.

들은 코드를 해석한다

html파일을 응답한다.

외에도 다양하다

파이썬으로 작성해야할 부분을 대신해준다. 

.gitignore 내부에 파일명을 넣어야한다. venv에 gitignore 사이트에서 받아오기

장고프로젝트 순위

1. venv
2. git init, ignore pip install  (requirements.txt 를 적어야한다.)
3. django 시작

기본 설정

1. python -m venv venv (아나콘다 사용하지마?)
2. touch .gitignore   vi .gitignore
3. source venv/Script/activate (윈도우 제외하면 bin에 있다)
4. pip install django==3.2.18
5. pip freeze > requirements.txt
6. django-admin startproject firstpjt   - 프로젝트의 시작 

      (자리에 생성 django-admin startproject testpjt .)

1. cd firstpjt/
2. python [manage.py](http://manage.py/) runserver

앱만들기

1. python [manage.py](http://manage.py/) startapp articles  - 앱생성
2. 

장고 extension 설치하면 html emmet이 안된다

프로젝트의 시작 - admin startproject firstpjt

어플리케이션의 시작 - python [manage.py](http://manage.py) startapp articles

manage.py는 무엇인가

장고하면서 는 go live 사용하지 않는다.

[settings.py](http://settings.py) 에 적으려면 임포트 가능해야한다…? 이단계는 필요없다???

localhost6000/articles

## 기본 원리

1. url만들고

프로젝트 내에 url내부의 patterns의 path에 url을 넣고 들어오면 url내의 views의 index함수를 실행해라. 뒤에 함수를 실행해야하고 views를 미리 임포트 해야한다.

1. view에서 함수를 만든다.

### templates - 절대 오타가 나면 안된다. s무조건 붙여라

```python
return render(request, "articles/index.html")
#render는 장고거다 app내부의 template으로 들어가 검색하는 함수
```

템플릿 내부 html에서 a태그를 활용할 때 조심할 부분이 있다.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>URL - VIEW - TEMPLATE</h1>
    <p>꼭 기억할 것</p>
    <a href="/articles/">articles</a> 
    <a href="/login/">login</a>
</body>
</html>
```

/articles/ 이렇게 적여야한다. 안그러면 /test/article/ 로 간다.

## 오류들

templates 오타

프로젝트에 installed_apps에 app안쓰면 template을 찾을 수 없다고 한다.
