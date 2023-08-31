# 알고리즘 개요

문제를 해결하기 위한 절차나 방법

## 의사코드 = 슈도코드

연습하자

## 좋은 알고리즘

정확성

작업량

메모리 사용량

단순성

최적성

좋은 알고리즘은 작업량을 줄인다. 

## 시간 복잡도

실제 걸리는 시간 - 연산의 횟수

## 빅오 표기법 O(n)

---

가장 큰 영향력을 주는 n에 대한 항만 표시한다.

숫자면 고정된 횟수를 갖는다. O(3) 같은 것

효율적인 알고리즘을 짜는 법. 더 작은 시간복잡도의 알고리즘을 할용할 수 있는가

10억번 연산은 = 1초 대략적으로

## 배열 : 하나의 이름으로 열거하는 자료구조

---

쉽게 편수 선언할 수 잇다 + 변수로 하기 힘든 작업을 배열로 활용 가능

- 1차원 배열

Arr = list() , Arr = [] 등등

Gravity 예제

[7,4,2,0,0,6,0,7,0] 오른쪽으로 90도 회전

오른쪽에 작은애가 몇개인가  그중 가장 큰 값을 찾으면 된다. ( 최대값 찾기를 직접, max값 생성후 비교 후 넣기)

알고리즘은 파이참 사용한다.

내장함수는 사용금지

크기 미리 정해놓고 풀기 append하지말기

- 정렬

내림차순, 오름차순

버블 정렬 (반드시 원리 이해)

카운팅 정렬 (반드시 원리 이해)

선택 정렬 (반드시 원리 이해)

퀵 정렬

삽입 정렬

병합정렬

### 버블정렬

---

인접한 원소끼리 자리를 교환하면서 맨마지막 자리까지 이동한다.

한단계가 끝나면 가장 큰 원소가 마지막 자리로 정렬된다.

교환하며 자리를 이동하는 물위에 올라가는 거품의 모양과 같다고 하여 버블정렬이라고 한다.

시간 복잡도는 O(n**2) - 효율적이지 않는데 어떻게든 돌아가겠군

두개씩 비교한다. 

첫번째 단계에서는 가장 큰 애가 맨 뒤로 간다.

두번째 단계에서는 두번째 큰애가 n-1로 간다. ….

가장 큰애를 밀어내는 정렬

이 작업을 

for i : n-1 → 1  (i는 구간의 끝)

for j : 0 → i -1

if A[j] > A[j+1]

A[j]↔ A[j+1]

## 파이참과 디버깅

---

파이참 - run으로 실행

주석 많이 달기

디버깅

파이참은 IDE

가상환경 다룰 수 있고 디버깅이 좋다. 

커뮤니티 붙은 소프트웨어는 무료버전이다. 장고 서포트는 지원하지 않는다. css java script도 지원하지 않는다. 그래서 vsc를 쓴다. 

VSC는 메모장 느낌

## 카운팅 정렬

각 항목이 몇개씩 있는지 세는 작업

시간 복잡도 O(n+k) k는 정수 최대값

- 제한 사항

정수나 정수로 표현할 수 있는 자료만 적용가능, 각 항목의 발생횟수를 기록한다.

ex) 0 - 9까지 리스트 만들고 숫자 있을 때마다 cnt = [0]*1000, cnt[i] += 1

충분한 공간을 할당하려면 집합내의 가장 큰 정수를 알아야한다.!!!

-포함이면 더해서 사용한다거나 유연하게 적용해야한다.

- 적용법

100만까지 가능하다. 인덱스가 10억이면 카운팅 정렬 못쓴다.

- 과정

cnt에 갯수 저장

cnt에서 자신의 앞에 있는 원소와 더한다.(카운트 변형)

현재 상태 : data counts(변형된 카운트) temp(정렬된 데이터) 

- 장점

원본의 숫자가 바뀌지 않아서 안전정렬이다. → 그래서 뒤부터 시작한다.

```python
a = list(map(int, input().split()))
size = len(a)
max_num = int(input())

cnt = [0] * (max_num + 1) #0부터 시작한다.
rlt = [0] * size

for i in a:
    cnt[i] += 1
for i in range(max_num):
    cnt[i+1] += cnt[i]  # 
for i in range(size-1, -1, -1):
    rlt[cnt[a[i]]-1] = a[i]
    cnt[a[i]] -= 1 #먼저 빼고 넣어도 된다 사소한 디테일 차이다. 매우 중요하당
		#cnt[a[i]] -= 1
		#rlt[cnt[a[i]]] = a[i] 이렇게 해도 괜찮다.

#역순은?

print(rlt)
```

## Baby-gin Game

세가지 카드가 연속적인 번호를 갖는 경우는 run 3장의 카드가 동일한 번호를 갖는 경우는 triplet이라고 한다.

6장의 카드가 run과 triplet로만 구성한 경우를 babygin으로 부른다.

## 완전검색 Brute -Force 브루트 포스 generate and test 기법

모든 경우의 수를 테스트 한다. 일반적으로 경우의 수가 작을 때 유용하다.

→ baby-gin에서 6개의 숫자로 만들 수 있는 조합을 모두 만들어본다.

## Greedy 알고리즘

이건 알고리즘의 접근 방식

**계속 최적화된 방법이 정답이 아닐 수 있다. (인생처럼^^)**

## 디버깅

---

옆에 점을 눌러야한다.

## Baby Gin - 발린다

바보의 코드

```python
cases = int(input())
for x in range(1, cases + 1):
    cnt = [0] * 10
    num_list = list(map(int, list(input())))
    for i in num_list:
        cnt[i] += 1
    run_v = tri = 0
    run_temp = 0
    for i in range(10):
        if cnt[i]:
            run_temp += 1
        else:
            run_temp = 0
        if run_temp == 3:
            min_v = min(cnt[i], cnt[i-1], cnt[i-2])
            run_v += min_v
            cnt[i] -= min_v
            cnt[i - 1] -= min_v
            cnt[i - 2] -= min_v
            run_temp = 0
    for i in range(10):
        if cnt[i] >= 3:
            tri += cnt[i]//3
    print(f'#{x} {(run_v + tri) // 2}')
```

정석 코드

```python
cases = int(input())
for x in range(1, cases + 1):
    cnt = [0] * 12 # 매우중요 12칸이 진짜 중요하다. 센스
    num_list = list(map(int, list(input())))
    for i in num_list:
        cnt[i] += 1
    runv = triv = 0
    i = 0
    while i < 10:
        if cnt[i] >= 3:
            cnt[i] -= 3
            triv += 1
            continue
        if cnt[i] and cnt[i+1] and cnt[i+2]:
            cnt[i] -= 1
            cnt[i+1] -= 1
            cnt[i+2] -= 1
            runv += 1
            continue
        i += 1
    print(f'#{x} {(runv + triv) // 2}')
```
