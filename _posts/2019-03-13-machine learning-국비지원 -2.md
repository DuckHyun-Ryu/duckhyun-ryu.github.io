---
layout : post
title : 국비지원 알게된 것 -2
subtitle : 국비지원 알게된 것 -2
category : machine learning
tags : 국비지원
date : 2019-03-13 17:30:00
---


(1).수정 가능한 자료형 (mutable): list, set dic

  수정 불가능한 자료형(immutable) : int, bool, float 등


(2). 포맷팅

   ex) print("%s결과 : %d%%+%d%% =%d" %("덧셈",3,4,3+4))

       print('{0}결과: {1}%+{1}% = {2}'.format('덧셈', 3,  3+3))

   두 번째 예시가 python에서 가지고 있는 장점

   같은 것을 쓰고 싶을 때 같은 {같은 숫자}를 넣으면 된다.

(3). 문자열과 관련된 함수

a. count

구조 : 대상.count('찾고자 하는 것')

결과값 : 찾고자 하는 것이 몇 개가 있는지 알려줌

b. find

구조: 대상.find('찾고자 하는것')

결과값 : 처음으로 찾고자 하는 것이 나온 index를 알려줌

주의 : 찾고자 하는 것이 없으면 -1을 결과값으로 도출

c. index

find랑 똑같음

주의 : 찾고자 하는 것이 자료형 안에 없으면 에러가 뜸

d. join

구조 : 대상.join(;넣고 싶은 것;)

결과값 : 자료형의 사이에 넣고 싶은 것이 들어감 , .이나, 같이 반복 되는 것을 한 번에 넣을 때 사용

주의 : 마지막에는 들어가지 않음



(4). 쥬피터 노트북 활용법

a. tab키 누르면 내가 활용할 수 있는 함수의 종류를 확인 할 수 있다.


(5). 복사

얕은 복사

a = [1,2,3,4]

b = a

b[0] = 10
p
rint(a)

이러면 a는 바뀐다. 왜냐면 주소값(본질)을 b가 a의 주소값을 받은 것이니 b를 바꾸면 a도 바뀐다.


하지만 만약에 b = a[:]

라고 하면 이것은 a의 데이터 자체를 빼서 b에 저장한 개념이므로 만약 b를 슬라이싱 해서 바꾸더라도 a는 바뀌지 않는다.

이것을 깊은 복사라고 한다.

(6). try except 구문

try except는 오류가 발생했을 때 그 오류를 무시하고 넘어가라는 의미이다.
if와 for과 똑같이 :을 사용하고 들여쓰기를 하면 된다.

태윤이형의 문제
1000원을 넣었을 때 숫자만 써달라는 메시지를 나오게 해라.

~~~
coffee =10
while True :
    try:
    money = int(input("money: "))
    if money ==300 :
        print("coffee")
        coffee = coffee-1
    elif money >300 :
         print("coffee and change %d" % (money-300))
    else :
        print("no coffee money back")
        print("remainder coffee is %d" %coffee)
    if not coffee :
        print("out of order")
        break
    except:
        print('숫자만 써주세요')
~~~

a. ''표를 하지 않은 것은 string도 뭣도 아니다.
b. except에는 무시하는 에러를 지정해 줄 수도 있다.
