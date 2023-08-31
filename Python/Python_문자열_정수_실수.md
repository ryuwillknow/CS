# 문자열과 정수, 실수

**string.lower()** 

**string.upper()**

split() - 공백을 기준으로 나눈다

split(’,’) - ,을 기준으로 나눈다

문자열 뒤집기

a[::-1]

- replace(a,b) 겹치면 안된다. 한방에 삭제
- replace(a,b) a가 없어도 된다. ㅋㅋㅋㅋ

리스트+문자열 = 리스트 + list(문자열) 이 되네 ㅋㅋㅋ?

## a = a.replace(b,c) 이렇게 써야한다.

## 소수점 다루는 법

1. round()

1. f string  print(f’{  “,.0f})

```python
menu = '스테이크'
menu_price = 50000
vat = 15

print(f'{menu}   {menu_price:,}\n + VAT      {menu_price*vat/100:,.0f}\n 총계      {menu_price+menu_price*vat/100:,.0f}')
```

a[1] 은 2번째

a[1:]은 슬라이싱

a[:x+1]을 조심하자

## .zfill

문자열만 가능하다.
