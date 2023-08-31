# Python 알고리즘 꿀팁

a[i][j]는 리스트가 아니다. 이건 하나의 값이므로 리스트처럼 따라가지 않는다.

## 오류의 기본

---

케이스의 부족 - 10개중 2개만

경계값

다틀리기 쉽지 않다. 

틀리고 고치는게 맞을까?

시간 복잡도

자료구조

정렬

무엇이 더 빠른가?

```python
import sys
a,b=map(int,sys.stdin.readline().split())
jokbo=[]
jok_dict = {}
for i in range(1,a+1):
    d=sys.stdin.readline().strip()
    jokbo.append(d)
    jok_dict[d] = i
for j in range(b):
    c=sys.stdin.readline().strip()
    if 47<ord(c[0])<58:
        print(jokbo[int(c)-1])
    else:
        print(jok_dict.get(c))
```

딕셔너리와 집합이 빠르다. 어떤 경우에서?

백주니를 따라가자.

## 브루트 포스 알고리즘, 전체 탐색

---

## 버블 탐색

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

if A[j] < A[j+1]

A[j]↔ A[j+1]

- 경우에 따라 if 두번 써야한다.

```python
cases = int(input())
for i in range(cases):
    size, group = map(int, input().split())
    num_list = list(map(int, input().split()))
    max_num = min_num = 0 # 최대값 최소값 변수에 저장
    gap = group // 2 # 차이를 gap에 저장
    for i in range(gap, size - gap): #gap만큼 빼도 된다 0부터 시작하므로
        i_sum = 0
        for j in range(i - gap, i + gap + 1): #왼쪽 오른쪽 gap만큼
            i_sum += num_list[j]
        if i_sum > max_num:
            max_num = i_sum
        if min_num == 0: #min이 0이라면, 없다면 + if 두번 써야합니다 !!!!!!!!!!!
            min_num = i_sum
        elif min_num > i_sum:
            min_num = i_sum
    print(max_num - min_num)
```

## 효율적인 알고리즘을 위해서는 컴퓨터 환경을 이해해야한다. 어떤 연산이 필요한가

## 소수점 다루는 것은 연산속도가 갑자기 늘어난다.

```python
ans = []
cases = int(input())
for x in range(1, cases+1):
    d, a, b, f = map(int, input().split())
    ans.append(f'#{x} {d/(a+b) * f}')
print(*ans)
```

## 평면 조심해라  2차원 배열

i = j * -1 은 없다

진짜 중요한거 !!! a[i][j] x, y가 아니다!!! i 가 y와 같은 세로다!

## 리스트 복사하는 법!!!

for 문안에 a[i][j]를 사용해서

a[i][j]는 리스트가 아니다. 이건 하나의 값이므로 리스트처럼 따라가지 않는다.

## 조건문 안에서 \의 의미

고수의 코드 진짜 고수의 코드

```python
for _ in range(1, 11):
    tc = int(input())
    ladder = []
    for _ in range(100):
        ladder.append(list(map(int, input().split())))
 
    for i in range(100):
        if ladder[99][i] == 2:
            y = 99
            x = i
 
    dy = [0, 0, -1]
    dx = [-1, 1, 0]
 
    while y != 0:
        for dir_idx in range(3):
            new_x = x + dx[dir_idx]
            new_y = y + dy[dir_idx]
 
            if (0 <= new_x < 100 and 0 <= new_y < 100) \
                    and ladder[new_y][new_x] == 1:
                ladder[y][x] = 0
                x = new_x
                y = new_y
 
    print(f'#{tc} {x}')
```

## 이중 for문 리스트 컴프리핸션으로 쉽게

이건 안쪽에서 시작한다. 2차원 배열 복제 이동할 때 잘 쓰인다. 잡기술

 + 돌리기가 돌리기가 아니다 90도만 가능하니까!!!!!

```python
def rot90(a, n):
    return [[a[n-i-1][j] for i in range(n)] for j in range(n)]

def rot90(a, n):
    rlt = []
    for j in range(num):
        temp = []
        for i in range(n):
            temp.append(a[n - i - 1][j])
        rlt.append(temp)
    return rlt
```

## 진짜 돌렸다 행렬돌리기

```python
def move_skin(i, j, lst, num, rlt, a):  # 오른쪽으로 a 칸
    circ = []
    for k in range(num - 1):
        j += 1
        circ.append((i, j))
    for k in range(num - 1):
        i += 1
        circ.append((i, j))
    for k in range(num - 1):
        j -= 1
        circ.append((i, j))
    for k in range(num - 1):
        i -= 1
        circ.append((i, j))

    for k in range(len(circ)):
        i, j = circ[k]
        i_b, j_b = circ[(k - a)%((num-1)*4)]
        rlt[i][j] = lst[i_b][j_b]

def move_lst(lst, num):
    rlt = [[lst[i][j] for j in range(num)] for i in range(num)]
    i = j = 0
    while num >= 1:
        move_skin(i, j, lst, num, rlt, num - 1)
        i += 1
        j += 1
        num -= 2
    return rlt

num = int(input())
lst = [input().split() for _ in range(num)]

for i in move_lst(lst,num):
	print(i)
```

행렬돌리기 다시

```python
a[i][j] => a[n-1-j][i]
#180 270 다 해보자!!!
```

## 컨디션이 안 좋은 건지 벽을 느낀건지 - 타이핑 문제

```python
cases = int(input())
for x in range(1, cases + 1):
    text, key = input().split()
    cnt = 0
    i = j = 0
    while i < len(text):
        if text[i] != key[j]:
            cnt += j + 1
            j = 0
            i += 1
        else:
            i += 1
            j += 1
        if j == len(key):
            j = 0
            cnt += 1
    print(f'#{x} {cnt + j}')
```

## 슬라이싱이나 해라!!!

```python
cases = 10
for x in range(1, cases + 1):
    size = 100
    num = int(input())
    lst = [input() for _ in range(size)]
    lst_con = [[lst[i][j] for i in range(size)] for j in range(size)]
    for i in range(size):
        lst_con[i] = ''.join(lst_con[i])
    max_num = 1
    for i in range(size):
        for j in range(size - max_num + 1):
            for k in range(j + max_num, size + 1):
                if lst[i][j:k] == lst[i][j:k][::-1]:
                    if k - j > max_num:
                        max_num = k - j
                if lst_con[i][j:k] == lst_con[i][j:k][::-1]:
                    if k - j > max_num:
                        max_num = k - j
    print(f'#{x} {max_num}')
```

나는 다 구해서 비교하는 방법을 사용

최고 높은 숫자를 구하는 방법은 그곳에 그것보다 큰게 있냐보다는 가장 큰 거만 

## 문제에 어떻게 접근할 것인가?

while 문 사용법

## 곱하기는 연산이 많이 든다

for x in arr + arr2 + arr3:

## 전치행렬 만들기

```python
arr_t = list(zip(*arr))  #요소가 튜플로 저장된다
arr_t = list(map(list,zip(*arr))) #리스트로 저장

# *은 한 겹만 벗긴다. 
# zip은 같은 길이의 여러 literable이 필요하다
# zip은 range, map과 같이 객체를 출력한다. 리스트로 바꿔줘야한다.

```

zip이 재밌다. 

## 꿀팁 for 문 변수 두개 - 그냥 별거 아니다. 실패!
