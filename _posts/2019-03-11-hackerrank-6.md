---
layout : post
title : Hackerrank 파이썬 문제 풀기-6
subtitle : Hackerrak 파이썬 문제풀기 -6
category : practice coding
tags : python
date : 2019-03-11 18:06:00
---

## 문제 
https://www.hackerrank.com/challenges/write-a-function/problem


## 풀이
~~~
def is_leap(year):
    leap = False
    if year % 4 != 0 or (year % 100 ==0 and year % 400 != 0):
      leap = False
    else:
      leap = True
    return leap

year = int(input())
print(is_leap(year))

~~~
