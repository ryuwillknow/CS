## 1 : 1 관계

한 테이블의 레코드가 다른 레코드 단 한 개와 관련된 경우

자동차와 엔진??

## N : 1

many to one relationships

여러 레코드가 다른 테이블의 한 레코드와 관련있다. 주문자 - 주문 내역

## M : N

태그, 좋아요

한명이 여러 개를 좋아요 누를 수 있다!

Foreign key는 다른 테이블의 유일한 값을 참조해야한다.

PK땡겨 쓴다.

## 실습 : 댓글 생성

댓글 = N : 1

comment 는 어떤 글인지 필요

장고는 

OneToOneField()

ForeignKey( to, on_delete, )

on_delete는 외래키를 참조한 객체가 사라졌을 때 외래키를 가진 객체를 어떻게 처리할 지를 정의한다. CASCADE는 부모 객체가 삭ㅈ됐을 떄 이를 참조하는 객체도 삭제

PROTECT, SET_NULL, SET_DEFAULT등 여러 옵션 값들이 존재

NOT NULL을 설정하는 법? 기본? 그럼 NULL 가능은 어떻게 만드는가?

comment의 article은 Article의 객체이다. 이게 중요하다.

comment.article.content

정방향 참조 = 안에 있는 field를 통해서 불러온다. comment.article.title  이런 느낌

하지만 Article에서 댓글을 찾고 싶으면 어떻게?  이게 역참조 이게 바로 Related manager ㅋㅋㅋㅋㅋㅋ

모델명_set = 모델명 매니져

object랑은 살짝 다른 느낌?

related_name = ‘comments’   이걸로 매니저 이름 설정 가능

exclude = ('article')

과연 새로운 view crud를 만들어야하는가?

save(commit=False)

현재 배운 것으로 댓글 수정은 새로운 페이지를 만들어야한다.

자바스크립트의 영역이다.

{% empty %}
