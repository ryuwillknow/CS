# 정렬모음

## 카운팅 정렬

```python
a = list(map(int, input().split()))
max_num = 1000
cnt_lst = [0] * (max_num + 1)
rlt = [0] * len(a)
for i in a:
	cnt_lst[i] += 1
for i in range(max_num):
	cnt_lst[i + 1] += cnt_lst[i]
for i in range(len(a)):
	cnt_lst[a[i]] -= 1
	rlt[cnt_lst[a[i]]] = a[i]

# 내림차순
a = list(map(int, input().split()))
max_num = 1000
cnt_lst = [0] * (max_num + 1)
rlt = [0] * len(a)
for i in a:
	cnt_lst[i] += 1
for i in range(max_num, 0, -1):
	cnt_lst[i - 1] += cnt_lst[i]
for i in range(len(a)):
	cnt_lst[a[i]] -= 1
	rlt[cnt_lst[a[i]]] = a[i]
print(rlt)
```

최대값 + 1만큼 카운팅 리스트를 만든다. 

결과값 리스트 만든다.

장단점

최대값을 알아야한다 - 카드에 사용가능?

정수일 때만 가능하다

빠르다.

안전정렬이다.

## 버블 정렬

```python
a = list(map(int, input().split()))
b = len(a)

for i in range(b, 0, -1):   # b를 b - 1로 만들고 i - 1을 i로 바꿔도 된다.
    for j in range(i - 1):
        if a[j] > a[j+1]:
            a[j], a[j+1] = a[j+1], a[j]
```

과정

순서대로 가면서 앞보다 크면 바꾼다!!! 점점 범위를 줄인다!

## 선택 정렬

```python
a = list(map(int, input().split()))
b = len(a)

for i in range(b):
    tmp_min = a[i]
    tmp_num = i
    for j in range(i, b):
        if tmp_min > a[j]:
            tmp_min = a[j]
            tmp_num = j
    a[i] , a[tmp_num] = a[tmp_num], a[i]
```

과정

구간에서 가장 작은값을 찾고 제일 앞에 둔다. 혹은 가장 큰 값을 찾고 뒤에 둔다.
