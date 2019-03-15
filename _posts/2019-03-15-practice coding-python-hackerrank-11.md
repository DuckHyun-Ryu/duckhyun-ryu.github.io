---
layout : post
title : hackerrank 문제풀기 -10
subtitle : hackerrank 문제풀기 -10
category : practice coding
tags : python
date : 2019-03-15 13:11:00
---

## 문제 

https://www.hackerrank.com/challenges/python-string-split-and-join/problem?h_r=next-challenge&h_v=zen

## 풀이

~~~
def split_and_join(line):
    line=line.split(" ")
    line = "-".join(line)
    return line

if __name__ == '__main__':
    line = input()
    result = split_and_join(line)
    print(result)
~~~

1. string의 split(구분자) 함수는 string을 구분자를 기준으로 문자열을 리스트로 만들어줌
2. string의 join함수는 리스트에 해당 문자를 중간에 집어 넣는 함수 
3. 그리고 string의 함수를 사용했다고 해서 해당 문자열이 바뀌는 것은 아님 
   바뀌려면 a = a.split() 이런식으로 다시 넣어 주어야함.
