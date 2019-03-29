---
layout : post
title : Hackerrank 파이썬 문제 풀기-7
subtitle : Hackerrak 파이썬 문제풀기 -7
category : practice coding
tags : python
date : 2019-03-11 19:00:00
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
알게된 것

1.list comprehension이란 리스트 안에서 for문을 사용한 조건의문문

2. 리스트 안의 변수 각각을 for 문으로 돌리는 것도 가능하다.

3. list comprehension의 구조 [expression for 변수 in expression for ~~ if 조건]
여기서 expression은 tuple, list , dictionary 등 여러 표현방법

4. range(a,b)가 나타내는 숫자 범위는 a 부터 b-1

5. 리스트 자체를 print 할수 있다. print(리스트)
