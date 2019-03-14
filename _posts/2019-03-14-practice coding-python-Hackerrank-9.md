---
layout : post
title : Hackerrank 문제풀기 -9
subtitle : Hackerrank 문제풀기 -9
category : practice coding
tags : python
date : 2019-03-14 13:14:00
---

## 문제

https://www.hackerrank.com/challenges/nested-list/problem

## 풀이 

~~~
f __name__ == '__main__':
    a = []
    b = []
    c = []
    for i in range(int(input())):
        name = input()
        score = float(input())
        a.append([name,score])  
        b.append(score)  
    
    for i in a:
        if i[1] == min(b):   ## a의 minimum 값 없애기
            a.remove(i)   
    
    d= (list(set(b)))       ## b의 minimum 값 없애기
    d.remove(min(d))

    for i in a:             ## 두 번째로 작은 값 찾기
        if i[1] == min(d):
            c.append(i[0])
    
    c.sort()               ## 알파벳 순서대로 나오기
    for i in c: 
        print(i)
~~~

하지만 위의 세 부분을 한 번에 해주는 풀이가 있다.

~~~
a=[]
b=[]
if __name__ == '__main__':
        for _ in range(int(input())):
                name = input()
                score = float(input())
                at+=[[name,score]]
                b+=[score]
        c=sorted(list(set(scorelist)))[1]     ## 두번 째로 작은 값 찾기

        for i,j in sorted(a):        ## 알파벳 순서대로 나오기
             if j==c:
                    print(a)
~~~
1. sorted 함수를 사용하면 정렬할 수 있다.
2. 중첩 list에서도 for을 사용할 수 있는데 이 때 문자를 2개 사용하면 된다.
3. 중첩이더라도 sorted를 사용하면 그 중 숫자의 영향으로 정렬이 된다.
