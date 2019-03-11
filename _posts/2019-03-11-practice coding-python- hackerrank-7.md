---
layout : post
title : Hackerrank 파이썬 문제 풀기-7
subtitle : Hackerrak 파이썬 문제풀기 -7
category : practice coding
tags : python
date : 2019-03-11 18:07:00
---

## 문제

https://www.hackerrank.com/challenges/list-comprehensions/problem

## 풀이
~~~
if __name__ == '__main__':
    x = int(input())
    y = int(input())
    z = int(input())
    n = int(input())

dimension = [[i,j,k] for i in range(0,x+1) for j in range(0,y+1) for k in range(0,z+1) if i+j+k !=n]
print(dimension)

~~~

1. list comprehension의 구조 [expression for 변수 in expression for ~ if 조건]
 여기서 expression은 list, tuple, dictionary 등 숫자가 많은 변수

 2. range(a,b)가 의미하는 숫자는 a에서 b-1까지

 3. print()의 괄호 안에 리스트, 튜플 등도 들어감.
