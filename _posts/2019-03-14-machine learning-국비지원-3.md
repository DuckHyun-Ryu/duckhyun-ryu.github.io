---
layout : post
title : 국비지원 알게된 것 -3
subtitle : 국비지원 알게된 것-3
category : machine learning
tags : 국비지원
date : 2019-03-14 17:27:00
---

(1). 리스트 추가

a. insert
구조 ; 리스트.insert(index, 넣을 값)
쓰임새 : 그 자리에 넣고 싶을 때 추가하는 기능

b. append
구조 : 리스트.append(넣을 값)
쓰임새: 맨 뒤에만 추가됨

c. extend
구조 : 리스트.extend(넣을 값)
쓰임새: append랑 똑같은데 집합형자료에만 가능
append랑 차이점은 리스트를 추가하려고 할 때 append로 추가하면 sublist로 들어가는데 extend는
sublist가 아닌 그냥 값으로 추가된다.

d. +=

(2). 디자인 패턴 : 개발 방법론

이것을 알고 모르고 하는 개발은 확연히 다르다.

(3). stack 구조

a.push : stack 구조에 넣겠다.
b.pop : stack 구조에서 빼내서 쓰겠다.
c.제일 늦게 구조에 넣은 성분을 pop을 이용하면 빠진다. 이런 구조를 stack구조를 한다.
d. b = a.pop()이라 하면 b에는 a의 제일 마지막 성분을 가지고 a에서 마지막 성분은 빠진다.

(4). 튜플
a. 변경이 불가
b. 리스트보다 속도가 빠르다.


(5). set

주의점 : set을 정의할 때는 a= set() 괄호 부분에 list 혹은 문자열이 들어와야 한다.
         문자열이 들어올 때는 하나하나씩 따로 set에 저장된다.

a. add()
구조 : set.add(없애고 싶은 값)
쓰임새 : 추가할 때 사용

b, remove()
구조 : set.remove(내가 없애고 싶은 값)
주의점 : 데이터가 없으면 오류
