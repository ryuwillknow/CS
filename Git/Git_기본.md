# GIT

컴퓨터 소프트웨어의 특정상태

누가 어떤 변경사항이 있었는지

변경사항, 누구 어디를 어떻게 언제

GIT은 변경사항으로 관리해준다. 

GIT : 분산버전관리프로그램

기존SVN : 바꾸면 파일 가져와서 다시 보내기. 시작하려면 다시 얻기. 중앙관리

GIT : 참여자들이 모두 소스코드를 다 가지고 있다. 

GIT - 동기화해주는

GITHUB - 저장소 서비스 ( 각 컴퓨터 외에 서버에도 소프트웨어가 있다.)

컴퓨터 사용법 

1) GUI : 클릭 입력 등으로 상호작용법 - 사람이 쓰기 편하지만 컴퓨터가 노력을 많이 한다.

2) CLI : 컴퓨터에게 명령어를 입력한다. 

# GIT 사용법

ls : 폴더의 내용물을 보여준다.

cd : change directory(folder), 더블클릭과 비슷하다.

cd .. : 빈칸 필요 (한칸 나오기)

touch : 파일 생성ㅅㅅ

mkdir : 폴더생성 ( 띄어쓰기 조심)

rm - r newre_dir  휴지통이동이 아니다.

xplorer 창이 뜬다.

-r  강제하다

/ 루트

상대경로, 절대경로

README - 마크다운으로, 이 프로젝트의 내용은 무엇입니다. 알려준다.

## GIT 시작

git bash - git init

프로젝트 폴더에서 git init 을 한다. - git이 생긴다

깃을 커밋( commit)한다 - 특정버전을 남긴다.

GIT의 세가지 영역

1. 프로젝트의 일부가 아닌 것
2. 프로젝트에 추가하고자하는 것
3. 프로젝트에 추가된 것

commit을 위해서는 3단계로 진행한다. 

1. git add 파일
2. git commit -m “ add 파일명”

git config --global user.email "you@example.com"
git config --global user.name햣"Your Name"

**순서**

1. 파일 변경생성
2. git add “  “
3. git commit -m “ “

## 상태확인

git status

git log ( 누가 어떻게 했나)

git log —online

git add . (현재폴더 전부)

## 오류 발생시 도망쳐

git add 하고 git commit 만 눌렀을 때 :q! 

git log 너무 길면 q누르고 도망쳐

## 권한 가져오기

git clone url

내가 그 권한을 가져오겠다.

## 이렇다고 github에 올라가는 것은 아니다.

git push 하면 소스코드를 올린다.

git clone  (shift insert)

## 사고 방지

git pull 매우 중요하다.

## 깃 연결 변경

git remote -v

git remote remove origin

git remote add

[깃 위티 독](https://wikidocs.net/149672)
