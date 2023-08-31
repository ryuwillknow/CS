# REVERT

GIT을 되돌리는 작업상태

Working Directory 상태

Staging Area 상태 - add 상태

Repository 상태  - commit 이후

### working directory

git restore 파일명 : 이전 커밋으로 되돌린다.

참고 - 이전에는 git checkout 사용, 너무 많이 사용해서 바꿈

### staging area

status 에서 newfile은 새로운 파일 추가이다. 

modify도 있다. 이미 있던 파일을 수정한 것을 없앨때는 restore사용

git rm —cached 파일명 : 새로 추가된 파일을 삭제한다.

git restore —staged 파일명 : 수정된 파일의 add 삭제  (다 된다??)

status 상태 주목

### repository : 두가지 경우의 수가 있다. staging area이 없을 때, 있을 때

git commit —amend 

i 누르면 작성가능 insert 

esc누르면 insert모드 나옴

:wq 하면 적용

가장 마지막 commit 이력에 대해서 메세지 수정할 수 있다. - 경우의 수 1 staging area이 없을 때

경우의 수 2는 직전 커밋을 덮어쓴다.!!!!!? 추가?

깔끔하게 원하는 파일만 올리고 내리고

### ETC

vi 파일명   하면 파일을 열 수 있다.

:w은 저장을 의미한다. 

:q는 종료를 의미한다. 수정 없이 나가기 x

:q! 수정 없이 나가기 강종

## RESET REVERT  : 내가 쓴 commit 되돌리기

### git reset

git reset —soft (앞에 4자리 이상 id)   :   그 시점으로 되돌리기!

git log — oneline 사용해도됨

—soft : 이전 것들은 대기상태로 들어간다.!!! (add 상태 stage 상태로 )  커밋만 삭제된다.

—hard : 그냥 삭제 (파일에서 ctrl z 가능)

—mixed : add 하기 전의 상태 ( 코드는 안바뀜)

### 교재에 없는 것

git reset id명  —mixed  기본값이다.

git reset HEAD~1 : 이전 커밋 (몇 개 가능)

### git revert : 특정 커밋을 없던 일로 만들어준다.

reset은 아직 공유하지 않은 작업을 할 때 사용한다??  충돌가능성이 높다. 

revert 는 그 커밋을 취소하고 새로운 커밋을 만들어준다. + 왜 지우려고 하는지 알려주자

겹치면 어떻게 되나여 ( 영화적이네 )

conflict 어떻게?

해결하고 git add 하고 git revert — continue 하여아한다. all conflict fixed

(적혀있음 reverting도)

commit의 사이즈는 팀 리더가 잡아준다.


