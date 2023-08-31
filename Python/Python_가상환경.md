# 가상환경

pip 파이썬 패키지 관리자이다.

pip uninstall requests를 하면 requests가 없어진다.

가상환경을 어떻게 (패키지의 버전을 관리한다.)

프로젝트마다 필요한 패키지가 다르다.

장고도 패키지다.

api request

이미지 pillow

bash 에서 

python -m venv venv_pjt1을 하면 

-m은 뒤에있는 모듈을 실행한다. 즉 python -m venv (venv_pjt1)

이렇게 만들면 프로젝트를 위한 패키지들이 들어있는 가상공간이다. 

bash에서

source venv_pjt1/Scripts/activate

하면 가상환경 시작  이 다음에 설치한다. install requestext

deactivate하면 가상환경 종료

사용하는 라이브러리가 다르다.  가상환경이 꺼지고 켜지는 환경에 따라

사용하는 파이썬이 다르다.!!! 가상환경 내의 파이썬을 사용한다.

폴더 이름 바뀌면 다른 파이썬 사용된다

가상환경을 실행한 상태에서 해야한다.

pip freeze - 버전 체크

pip freeze > requirements.txt 하면 메모장으로 생성

pip install -r requirements.txt

bash는 윈도우즈를 유닉스처럼 사용하게 만들어준다.

**가상환경은 GIT에 올리면 안된다. (like cache, data, json)**

⇒ .gitignore

이 파일 안에 기록된 파일은 git이 무시한다.
