# django2
디자인패턴은 공통적으로 발생하는 문제에 대해 해결책을 제시해준다.

장고는 MTV패턴

MTV  는 MVC디자인 패턴을 조금 변형했다.

url로 오면 view에서 model로 가거나 template으로 간다

## django template :  데이터를 표현

동적인 컴텐츠를 넣을 것이다.

DTL : django template language

조건을 걸 수 있다. 반복 변수 필터 등등

파이썬 언어를 실행하는 것이 아님. dtl에서 일부 기능을 제공한다. 

공식문서에 가서 해봐야한다.

variable은 변수다

filter는 변수가 보여지는 것을 바꿔준다.변수는 안바뀜

tags 

comment 주석

```python
def index(request)
	name = 'aiden'

	info = {
		'name' = 'aiden'
		'age': 21
	}
	return render(request, template_name, {info: info})

# 사실 render는  context가 있었다.
# html템플릿에서 
# {{info. age}}여기에
# {{info. name}}

```

## Filters

```python
{{ variable| filter}} 이렇게 사용한다.
{{ variable| lower, add 2 }}
```

일부 필터는 인자를 받기도 한다. lower도 있다. 60개의 빌트인 tmeplate filtters가 있다.

## Tag

```python
{% if %}
{% endif %}
```

24개 tag제공

## Comment

```python
{% comment %}
	여러줄 주석
{% edncomment%}
```

## 템플릿 상속

중복방지, 재사용성 높이기 위해서 한다.  

```python
{%extends ''%} # 자식 템플릿이 부모 템플릿을 확장한다. 반드시 최상단

{% block content %} {% endblock content%}
#하위 탬플릿이 채울 수 이쓴 공간을 만들기

```
