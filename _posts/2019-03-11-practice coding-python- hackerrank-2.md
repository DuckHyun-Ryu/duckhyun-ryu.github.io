---
layout : post
title : Hackerrank 파이썬 문제 풀기-2
subtitle : Hackerrak 파이썬 문제풀기 -2
category : 코딩문제모음
tags : python
date : 2019-03-11 18:02:00
---

## 문제

https://www.hackerrank.com/challenges/py-if-else/problem

## 풀이
~~~
N = int(input())

if N % 2 ==1:
  print ("Weird")
elif N % 2 == 0 and 2<= N <= 5:
  print ("Not Weird")
elif N % 2 ==0 and 6<= N <= 20:
  print ("Weird")
else:
  print ("Not Weird")

~~~
