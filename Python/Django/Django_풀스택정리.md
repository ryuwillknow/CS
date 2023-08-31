# django full stack
드루와 가장 기본적인 것부터 시작해서

웹서비스는 클라이언트 서버 구조로 동작한다.

클라이언트(웹 브라우저)가 requests을 보내면 server가 responses를 보낸다. 

requests는 다양하다. url, submit, 외에도 많다.  일단 두가지 방법을 중점적으로(23.03.20) url과 submit

가상환경 필요한 것

django, ipython, django-extensions

앱은 복수형으로 만드는 것을 추천한다.

파이썬은 [manage.py](http://manage.py)를 활용해서 장고와 소통한다. (기본적으로 실행하는 파이썬파일을 기준으로 경로가 설정된다. from import를 조심하자)

장고가 독립적인 파이썬 서버를 만들어주는 것이 아니다. 장고라는 틀안에 파이썬 파일 생성해준다. 이말인 즉슨 개별적인 파이썬 파일들은 거시적으로 완벽하지 않다. 파일 간의 이동을 논리적으로 완벽하게 보여주지 않고 장고 내부에서 수행하는 경우가 많다. 대신 사용자가 변경하고 응용할 수 있는 부분을 남겨두었다. urls, views, model이 그렇다.

그랬을 때 요청이 가장 먼저 도착하는 곳은 project의 urls.py이다.

프로젝트 설정은 settings.py에서 조정한다.

[manage.py](http://manage.py)는 장고 서버를 실행해준다. 때문에 실행위치가 고정이 되고 내부 프로그램의 기준이 실행위치가 된다. manage.py는 정말 실행을 시켜준다.

요청의 종류는 여러가지가 있다. 그것을 project urls.py에서 분류한다. 이게 있는지. 있다면 어디로. 없으면 오류를 내보내주던가 장고가 특정페이지로 인도해준다.  - 이런 것을 컨트롤 하는 부분은 알아서 찾아봐야한다. 

### 전체적인 큰 흐름

프로젝트 urls - app urls - view - template

MTV는 어디서 오는가 이걸 추가

### [urls.py](http://urls.py) 프로젝트와 앱에서

가장 먼저 해야할 것은 django.urls에서 path 함수를 불러온다.

urlpatterns는 리스트 이고 여기서 path함수가 주소와 가야할 위치를 변환해준다. 

path 함수는 변수와 함수를 구분한다. view속 함수로 바로 지정하던가, include를 통해 앱의 urls로 보낸다. 단 바로 지정하는 것은 추천하지 않는다. 나중에 어짜피 앱내부에서 할 일이다.

여러개의 view가 필요하면 import view as 어쩌고 이렇게 가져온다.

앱내부의 usls.pay에서 path에서 이름을 설정할 수 있다. +  view불러올 때 경로에 유의해야한다.

만약에 variable routing이라면 {% url ‘name’ 변수 혹은 str %}를 적어줘야한다. 이건 그 url이 어떤 것을 요구하느냐에 따라 달려있다. 오류 종류는 **NoReverseMatch**

 

가장 말단 urls에서는 반드시 view로 연결해줘야한다. 즉 이 urls 요청이 오면 이런 함수를 실행해줘.

그 함수는 일반적으로 html을 보내준다. (일단은 나중에는 데이터 베이스를 변경하고)

단 어떤 urls 요청 + 추가 사항은 데이터 베이스를 crud한다.  urls요청이 그 주소의 html도 있지만 데이터 베이스 변경, 불러오기, 등등의 요청도 수행한다…? urls에 submit할 정보와 함께 요청?

### [view.py](http://view.py) 내부에서는 함수가 존재한다.

그 함수는 return을 render 혹은 redirect함수를 해준다. 

모든 함수는 request를 받는다. 이 request는 장고가 받아준다. request는 form을 통해 보낸 정보들을 포함해 여러가지를 갖고 있다.

request는 어떤 구조로 이루어져 있는가.  token, method, data, file, static 등이 딕셔너리로 갖고 있다. querydict인듯?

함수를 실행시키려면 urls가 필요하다. request를 활용하던 활용하지 않던 다른 사이트로 보내던 데이터 베이스를 접근하던 수정하던. 그 창을 띄워주지 않아도 된다.  

request.GET  request.POST는 QueryDict이다. 

dict내부에 form의 내용이 있다. id? name? 이거 명확하게 보자.

request.method는 request의 method를 보여준다. GET POST 이런 식이다.

이 함수의 return이 중요하다. 일단 두가지 render와 redirect

render(request, templates주소, context)  # templates의 주소는 app내부의 templates 폴더이다. 

render함수는 context, request,template주소를 render to string 으로 변경한 후 content에 담아 httpresponse클래스(함수인줄 착각했다)에 넣어 return한다.  (이 클래스로 이렇게 저렇게 하는거지)

즉 render 대신에 httpresponse를 넣어도 된다.  (httpresponse는 str형태의 html을 받는다. 아마 이걸 다른 신호로 바꿔줄 것이다.)

즉 context와 request, template을 짬뽕해서 str로 바꾸고 httpresponse에 넣은 걸 return한다.

context는 딕셔너리 형태여야한다. 변수와 매칭하면된다.  { ‘name’ = name }

여기서 가끔 request와 다른 변수를 받는 경우가 생긴다. 이거 중요하다.!!!! - variable routing이라고 한다.

단 조심해야하는게 <str:name>을 받으면 겹치는 것이 없어야한다. 다른 주소가 있으면 str:name만 읽힌다.

path에 다음과 같이 등록

```python
path('hello/<str:name>/', include(articels.urls))

#그러면 다음과 같이 받는다.

def hello(request, name):
	context = {
		'name' : name
	}
	return render(request, 'hello.html', context)
```

path의 name에 대해서 : appname이 있으면 하이퍼 링크에서 {% url ‘appname:view’ 5} 로 연결가능 appname없으면 그 자체로 가능

redirect(urls)

### 잠시 Templates로 넘어온다.

settings DIR에서 templates의 base파일 폴더를 설정할 수 있다. 이를통해 앱간의 기본적인 템플릿을 정립할 수 있다. 단 templates 폴더를 최상단에 두어야한다.

```html
{% extends 'base.html' %}

{% block content %}

{% endblock content %}
```

장고의 템플릿언어 Django Template Language  A.K.A DTL

```html
{{ variable }}
{{ variable|filter }}  ex) {{ variable|lower }}  {{ variable|truncatewords:30 }}

{% if %}{% endif %} {% for in %} {% endfor %} 
```

여기에 변수가 필요하다. 변수가 필요한 html과 변수의 정보가 dictionary 형태로 저장되어 있는context와 request를 render가 섞어서 str로 바꾸고 httpresponse에 넣어서 보낸다. 

- 왜 갑자기 2개가 되는가

path() 혹은 url()이 인자를 만들어준다. 이 인자를 장고에서 자동으로 함수에 넣고 실행시킨다는 뜻이다. 이 인자를 함수에서 받지 않으면 오류가 난다. Typeerror

urls에 대한 설명 블로그

https://blog.hannal.com/2014/11/start_with_django_webframework_05/

### Form & Data 이제 진짜 시작이다

장고가 갖고 있는 것은 3가지?  urls request  → path가 인자와 request로 바꾸고 함수를 실행한다. 

```html
<form action="" method""> </form>
```

form은 url을 담고 있다.(url, name사용가능, 즉 같은 url이어도 view에 if문을 적용해서 POST와 GET을 구분해서 가능하다) method는 GET아니면 POST이다. 이건 request내부에 저장된다.  form내부에서 받은 정보들은 request의 querydict에 담는다.!!!! 딕셔너리의 형태이다. 나중에 view함수에서 request를 뽑아서 쓸 수 있다.  request.GET  [request.POST](http://request.POST) 이런 식이다.

input태그는 사용자로부터 데이터를 받기 위해 사용한다. 

type과 name에 집중하자. type이 아무것도 없다면 text이다. name은 querydict의 key에 해당한다.

id는 label태그에 사용된다. label을 클릭해도 input할 수 있도록

http와 request  표준을 맞추기 위해서  form의 request는?

클라이언트와 서버는 http로 요청과 소통한다. view함수에 들어가는 request는 http를 변환한 것

주소창이 아닌곳에서 input을 받는 법 form # 이건 지금은 못한다. keep하자

javascript와 관련있다. 

### Datebase 기본 구조

스키마와 테이블  

스키마는 데이터 베이스에서 자료의 구조, 표현방법 관계를 정의

테이블은 데이터 요소들의 집합  relation이라고 부름  테이블에서 field 는 col  record는 row

pk = primary key  기본키 각 레코드의 고유한 값  절대로 중복될 수 없다. 

Query : 데이터를 조회하기 위한 명령어 querydict와는 다르다?

Query string 은 ?test=alskdf&password=alskdf 이거다 (input을 통해서)

장고는 Model을 통해 데이터에 접근하고 조작한다.

일반적으로 각각의 모델은 하나의 데이터 베이스를 매핑한다. 모델 클래스 1개는 데이터베이스 테이블 1개 - 클래스 여러개는 테이블 여러개   Model(model.py)

app 내부의 model.py에 class를 작성하는 것은 테이블의 스키마를 정의한다. 

호기심천국, 함수와 클래스 이용법 urls view template은 함수를 불러왔다.

함수는 들어오는 것을 가공한다. path는 url과 view함수를 가져와서 변환. 검색하기 쉽게  view함수는 요청과 변수를 활용해 데이터베이스를 만들거나 html을 완성한 후 최종 httpresponse 객체를 보낸다.

이번에는 클래스다. 

[settings.py](http://settings.py) app설치 목록에 반드시 추가

migration 적용사항들을 저장하기 위해서

makemigrations    한번에 모든 앱  이놈은 만들어만 준다. 잘못만들면 다시 지우고 만들어야한다.

migrate  스키마 적용 이거 안하면 데이터베이스에 변화가 없음  새로열어줘야한다.!!!  꺼지면

여기에 shell plus는 migrate이 된 상태에서만 작동한다. 아니면 shell plus —plain으로만 켜진다.

sql과 python

orm이 언어(query?)를 변환해주고 결과(queryset?)도 변환해준다. 

manger인 objects는 자동으로 추가된다.

이런 필드는 이런 속성을 가지고 있다. 는 개념을 파이썬 언어로 표현하려면 

거기에 view 함수 내에서 이 정보를 사용하자는 개념을 사용하려면 어쩔 수 없이  클래스를 사용하면 아하 데이터베이스를 다루는 구나

django-extensions으로 shell plus를 사용할 수 있다. 여기에 사용하는 명령어를 view함수 내부에 사용한다.  - 이거 딱 그 데이터베이스 통신 코드 뿐만아니라 다른 것도 다 적용이 된다. shell_plus는 그냥 파이썬으로 실행하면 안되니까 장고의 설정을 가져와서 실행한다. + 파이썬으로 실행하는 것이 아닌 manage.py로 실행한다. shell_plus는 도우미

Model은 ModelBase의 것 여기서 매니저를 지정하지 않으면 objects 매니저를 contribute to class한다. 이 클래스는 Manager클래스를 따른다. 여기에 Manager클래스의 함수가 다 적혀있다. 

아마도 클래스가 있으면 이걸 ORM에 바로 실행시키고 그 결과를 받지 않을까 생각한다. - 추측 아니다. 

ORM은 데이터베이스와 소통하는 언어가 아니다. 객체를 바꿔주는 기능을 한다. 

### CRUD

방법에 대해서 여러가지

### Django form과 Django html

기본 form은 유효성 검증이 어렵다.

forms.py를 만들고 from django import forms 한다. 그리고 클래스를 정의한다. forms.Form

받고 싶은 개수와 속성

form.as_p는 form안에 넣어준다.  사실 form을 대체하기 보다는 틀 내부에서 유효성 검증을 자동으로 해주는 것이다. 이거 models의 form과 연동시키는 것이 중요하다.  이름바꾸기는 어떻게 하는가? label로 한다.

## 제대로 가자가자

request - url에 보내지는 정보, form의 정보를 내포하고 있다. 일단은

request.GET  [request.POST](http://request.POST)  이것들이 querydict형태이다.

request.data도 있다

여러가지 방법이 있었다.

일단 기본적으로 models.py에서 데이터의 형태를 정의해줘야한다. - makemigrations 안 해줘도 admin에서 추가 가능하다?

[models.py](http://models.py) 에 추가하면 총 세가지 방법으로 데이터 베이스와 소통할 수 있다.

[models.py](http://models.py) 의 model을 가져와서 객체 생성 후 model.title = request.POST[’title’]  save()활용

models(title=’title’, content = ‘content)  직접 문자열을 넣어줄 수도 잇따.

아니면 models.objects.create  models.objects.all() models.objects.get(pk=1) 등 objects 매니저를 활용(모델의 메니저)

save()매서드 사용가능 form modelform 도 가능하다

modelform은 내부에 meta클래스에 어떤 모델을 상속했는지와 field를 지정해준다

일반 form은 request.post.get(’title’) 을 모델에 직접 넣아줘야한다. save없음 model객체.save해야함

여기서 중요한것은 form객체.save()는 정보를 return한다. form객체.pk는 생성정보  post후 해당 페이지로 버낼 때

update는 불러와서 save()활용 delete는 객체의 delete()매서드 사용한다.

인증의 form은 그냥 이다. 로그인!.[form.py](http://form.py) xxx model.py에 user머델 추가해야한다

일단 뒷부분 :

many=True를 안하면 attribute error가 뜬다.

post는 딕셔너리 형태로  status.HTTP_201_CREATED  status.HTTP_400_BAD_REQUEST

역참조 - many = True  read_only

정참조 이름 맞추기

raise_exception

read_only_field 는 튜플형태로 serializer의 meta에 추가한다.

get_object_or_404

def to_representive

post에 article = article

source=comment_set.counts  read_only

---

공식문서는 신이다. 내부의 것들을 다 설명해주고 있다.(아니었음) + 블로그도 신이다

질문 목록  shell plus —plain이어야 실행되는가

왜 클래스인가 ( 이런 클래스면 이런 기능들을 사용할 수 있다. 이런 정보를 넣어줌? 내가 알던 클래스와 느낌이)

Article이 클래스를 불러오는데 따로 선언을 안해도 이 자체가 개념이 있는 느낌? 왜? 가능?

클래스 변수와 클래스 매서드는 이렇게 사용이 가능하다!!!

쿨팁 : →

def something(a : int) → None: a 변수는 int고 None을 반환한다는 주석이다.

accounts.User : 얘는 장고맘이다. 조금만이해하자

해야할 일…  구현 안해본것 정리 안한 것

form.get_user (로그인 로직)

회원가입후 바로 로그인할 때 user = form.save()   login(request, form.get_user())

로그인 과정

오류에 대해서

틀리면 바꿔준다. - authenicationform   회원정보 수정에 넣기는?

meta field

데이터는 객체를 통해서 주고 받는줄 아는데 로그인은 아니다.
