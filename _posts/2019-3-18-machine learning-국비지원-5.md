---
layout : post
title : 국비지원 알게된 것 -5
subtitle : 국비지원 알게된 것-5
category : machine learning
tags : 국비지원
date : 2019-03-18 18:22:00
---

(1) argument 와 parameter

함수에서 실제로 받는 인자를 argument라고 한다.
함수의 정의에서 사용 되는 인자를 parameter라고 한다.

(2) 전역변수, 지역변수

전역 변수와 지역 변수의 이름이 똑같으면 가까운 지역변수를 사용한다.

(3) global
바깥에 있는 전역변수를 쓰겠습니다.

사용법 : 'global 변수이름'를 함수정의 맨 처음에 선언한다.



(4) defalut 인수

def 함수이름(전역변수이름 = blahblah):

바뀌지 않는 변수들은 앞에 변수이름을 정하자





(5) 가변 인수

a.함수의 인자가 list 즉 성분이 많은 자료형 들도 하나의 인자에 넣을 수 있다.
리스트로 넣기 싫다면 함수의 인수 앞에 * 를 붙이면 된다.
* 로 여러 인자를 받으면 튜플로 저장된다.

참고 :변수를 여러 개 선언 할 때도 * 를 사용해서 변수를 선언할 수 있다.
나머지는 리스트로 받는다.


b. ** 두개로 받으면 함수의 인자를 dict로 받을 때 사용
   이것도 가변인수 이므로 여러 개의 변수를 받을 수 있다.



(6) 여러가지 내장함수

a. divmod(a,b) : 몫과 나머지를 리턴값으로 반환 해주는 함수

b. enumerate(a.b) : 순서가 있는 자료형을 입력받아 인덱스 값을 포함해서 리턴

c. eval(표현식) : 표현식을 파이썬에서 실행 가능하게 만들어 주는 역할

d. map(함수, 집합자료형) : 집합의 각 요소가 함수에 의해 수행된 결과를 묶어서 리턴
