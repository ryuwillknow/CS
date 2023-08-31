# 문자열

각 문자에 대응하는 숫자를 정해놓고 이것을 메모리에 저장한다

처음에 지역마다 기준이 달랐으므로 혼동을 피하기 위해 표준안을 만들었다.

→ ASCII(American Standard Code for Information Interchange)라는 아스키 코드

ASCII

7bit인코딩 128문자를 표현

33개 출력 불가능한 제어문자

95개의 출력가능한 문자

확장 ASCII 는 악센트 도형 특수문자 등 128개를 추가한다.

이것은 자기 마음대로

다국어 처리를 위한 표준 → 유니코드 ( 16진수라고 하네요)

이 영역에는 각자 언어를 넣는 것으로 한다.

bit - 0,1  byte - bit 8개 뭉쳐서 하나의 단위

ABCD - 4byte

묶었을 때 장점 

메모리 = 주소, 데이터, 제어 

주소 표현할 때 bit면 너무 길어진다. 그래서 최소단위는 byte이다.

16진수가 왜 튀어나오나

한 byte 는 16진수 2자리로 표현가능하다  편하게?  **0 - 9  a - f !!!!!!!!!!!!!!!**

a4 9b 이렇게 편하게 보자!

컬러에서 사용된다!!! color: #1FB9A6

유니코드도 다시 Character Set으로 분류된다.

UCS - 2(Universal Character Set 2)

UCS - 4(Universal Character Set 4)

인코딩이 필요하다… ex) ‘대’는 B300일때 이것을 변환해준다

유니코드 인코딩

UTF - 8 (web, python)

최소 8비트 최대 32비트

UTF - 16 (window, java)

최소 16비트 최대 32비트

UTF - 32 (unix)

최소 32비트 최대 32비트

P대 

50 EB 8C 80

EB 8C 80 = 1110 1011 1000 1100 1000 0000

1110 - 기본 코드  10으로 구분한다 → 대로 만들어준다

UTF - 16도 다르다

CRLF - 윈도우 포멧 엔터

LF - 리눅스 포멧 엔터  

CRLF 는 출력 불가능한 제어문자

C언어는 문자열을 저장할 때 마지막에 널문자를 넣어줘야한다.

==연산자는

```python
__eq__() #를 호출한다
```

is는 깊은 같음? 같은 애를 가르키고 있는가

‘abc’[:2] + ‘c’ is ‘abc’ 이건 False

파이썬은 캐릭터 타입이 없다 char이 없다. 다른 언어에는 있다.

```python
'''
'''

# 따옴표 3개 사용한 문자열은 엔터 인식한다.
```

조금 더 잘해보자  string은 슬라이싱을 많이 사용하자

```python
def abba(lst, i, j, n, m):
    rlt = ['','']
    if i + m - 1 < n:
        for k in range(m):
            rlt[0] += lst[i+k][j] #가로
    elif j + m - 1 < n:
        for k in range(m):
            rlt[1] += lst[i][j+k] #세로
    return rlt  # 이부분을 슬라이싱으로 사용해도 된다.
 
cases = int(input())
for x in range(1, cases + 1):
    n, m = map(int, input().split()) 
    lst = [list(input()) for _ in range(n)]  #리스트로 받지 않고 그대로 받은 다음에 슬라이싱
 
    ans = ''
 
    for i in range(n): #범위 설정
        for j in range(n):
            for k in abba(lst, i, j, n, m):
                if k != '' and k[::-1] == k:
                    ans = k
            if ans:
                break
        if ans:
            break
 
    print(f'#{x} {ans}')
```
