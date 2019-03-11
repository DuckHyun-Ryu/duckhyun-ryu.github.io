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
