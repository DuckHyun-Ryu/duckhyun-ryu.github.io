---
layout : post
title : hackerrank 문제풀기 -8
subtitle : hackerrank 문제풀기 -8
category : 코딩문제모음
tags : python
date : 2019-03-11 20:00:00
---

## 문제

https://www.hackerrank.com/challenges/python-mutations/problem?h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen&h_r=next-challenge&h_v=zen

## 풀이

~~~
def mutate_string(string, position, character):
    a = list(string)
    a[position] = character
    string = ''.join(a)
    return  string

if __name__ == '__main__':
    s = input()
    i, c = input().split()
    s_new = mutate_string(s, int(i), c)
    print(s_new)

~~~

1. string을 그냥 리스트로 바꾸면 한문자 한문자가 리스트로 저장되므로 split을 사용하여 내가 원하는 단락을 리스트로 만들수 있다.

2. 리스트를 그냥 string으로 바꾸면 리스트 대괄호까지 전부 string으로 바뀌기 때문에 안에 있는 성분만 string으로 바꾸기 위해서

   join함수를 써서 string으로 바꾼다. 넣고 싶은 구문자.join(리스트)  리스트->string
