---
layout : post
title : Hackerrank 파이썬 문제 풀기-8
subtitle : Hackerrak 파이썬 문제풀기 -8
category : practice coding
tags : python
date : 2019-03-12 18:10:00
---

## 문제 

https://www.hackerrank.com/challenges/find-second-maximum-number-in-a-list/problem

## 풀이
~~~
n = int(input())
arr =  list(map(int, input().split()))

arr = list(set(arr))
for i in arr:
    if i == max(arr):
        arr.remove(max(arr))
print(max(arr))

~~~

1. map 함수 구조
   map(함수, 리스트)면 리스트의 모든 성분에 함수가 걸린다.

2. 만약 리스트를 인풋으로 받고 싶으면 map(int, input().split())
   여기서 split은 공백에 input으로 받은 숫자들을 공백을 기준으로 나눈다는 뜻이다.

3. map은 리스트가 아닌 map이라는 type이므로 리스트로 바꾸고 싶다면 앞에 list를 붙여준다.
   정리하면 리스트를 input으로 받고싶다면 list(map(int,input().split()))) 이라하면 된다.

4. for문을 돌기 전에 list의 반복 성분을 없애야 하는데 방법은 list(set(내가 원하는 list))
   set은 중복이 없기 때문에 set으로 type을 바꾸면 중복이 날라가고 다시 list로 바꿔주면 된다.
