---
layout : post
title : Hackerrank 파이썬 문제 풀기-13 Find a string
subtitle : Hackerrak 파이썬 문제풀기 -13 Find a string
category : practice coding
tags : python
date : 2019-03-16 14:20:00
---

## 문제 

https://www.hackerrank.com/challenges/find-a-string/problem

## 풀이 

~~~
def count_substring(string, sub_string):
  count = 0
  start  = 0
  end = len(sub_string)

  for i in range(len(string)-len(sub_string)+1):
    if string.find(sub_string,start,end) != -1:
      count +=1
    start+=1
    end+=1
  return count

if __name__ == '__main__':
    string = input().strip()
    sub_string = input().strip()
    
    count = count_substring(string, sub_string)
    print(count)
~~~

1. find함수는 한 글자만 알려 주는 것이 아니라 sub_string이 list[start:end]안에 있으면 알려준다.
