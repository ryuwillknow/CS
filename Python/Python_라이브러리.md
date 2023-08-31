## 라이브러리 정리

https://docs.python.org/ko/3/library/index.html

표준 라이브러리

re : 정규식 찾기, 기점으로 쪼개기, 교체, 

datetime : 날짜를 나타내는 객체, 정확하게 표현해줌

```python
from datetime import datetime 
print(datetime.now())
# 이게 더 정확하다고 한다.

# 일반적으로 time을 가져온다. 시간 잰다.
print(time.time())
# 1687563245.109716
```

collections : deque, Counter(얘는 클래스라 대문자)

```python
# counter는 얼마나 반복되는지 저장하는 딕셔너리, 산술 연산도 가능하다.
import collections
print(collections.Counter('asdfasdf'))
# Counter({'a': 2, 's': 2, 'd': 2, 'f': 2})

# deque는 왼쪽 오른쪽 다 뺄 수 있다.
```

heapq : heappush, heappop, heapify

```python
h = []
heappush(h, (5, 'write code'))
heappop(h)
```

copy : copy, deepcopy

pprint : pprint(depth = 길이 이후 …,  indent = 들여쓰기 간격,  width = 넓이

numbers : 숫자 추상 베이스 클래스  이건 딱히 안 쓴다.

math : ceil, log, sqrt , acos, asin, atan, e, pi, factorial, gcd(최대공약수)

```python
from math import
```

random : seed(난수 생성기 초기화), randrange(사이의 값중 하나), choice(시퀀스 중 하나 고르기), choices( 중복허용 여러개 반환), shuffle, random(0 - 1 사이)

itertools : 무한 생성 : count, cycle, repeat, product(repeat=2), combinations, permutations

threading, multiprocessing, queue(동기화 큐)

email, json

turtle : 아기용 그림그리기

tkinter : 윈도우 창 만들기

bisect : 이진 탐색!!!

## 내장함수

abs : 절대값

bin : 이진수  hex : 16진수  oct : 8진수

chr, ord

enumerate

eval : 문자열 계산해줌

filter : 함수 true인 것만 뺴줌

open : 파일 객체

round(반올림)

with open as

파일을 열고 구문이 끝나면 자동으로 닫는다.
