---
layout : post
title : 파이썬 중급14-comprehension
subtitle : 파이썬 중급14-comprehension
category : 프로그래밍 언어 공부
tags : python
date : 2019-05-22 12:40:00
---

# list comprehensions

for문이나 if문을 list안에 넣어 list의 생성을 조건식으로 할 수 있는 방법입니다.  


1부터 10까지의 정수를 순서대로 가지는 리스트를 만드는 예제를 한 번 보겠습니다.  


```python
a = [x for x in range(1,10)]
a
```




    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]



이번에는 1부터 10중에 짝수만 출력하는 조건을 걸어보도록 하죠.


```python
a = [x for x in range(1,10) if x % 2 ==0]
a
```




    [2, 4, 6, 8]



### 중복표현
comprehension은 for과 if를 몇 번이고 반복할 수 있습니다.  

저녁으로 먹을 메뉴 '쌈밥', '치킨', '피자' 중 하나와 후식으로 먹을 '사과', '아이스크림', '커피'를 정할 때 가능한 경우의 수를 뽑는 코드를 컴프리헤션으로 작성해보겠습니다.  


```python
[(x,y) for x in ['쌈밥', '치킨', '피자'] for y in ['사과', '아이스크림', '커피']]
```




    [('쌈밥', '사과'),
     ('쌈밥', '아이스크림'),
     ('쌈밥', '커피'),
     ('치킨', '사과'),
     ('치킨', '아이스크림'),
     ('치킨', '커피'),
     ('피자', '사과'),
     ('피자', '아이스크림'),
     ('피자', '커피')]



이렇게 뒤에 있는 for이 앞에 있는 for안에 걸리는 이중 for문이라고 생각하시면 편할 것 같습니다.

if도 똑같이 중복해서 여러가지 조건을 걸 수 있습니다.   
1부터 10중에 5보다도 작고 짝수인 값들을 리스트에 담아봅시다.  


```python
[ x for x in range(10) if x < 5 if x % 2 == 0 ]
```




    [0, 2, 4]



x가 5보다도 작고 짝수인 값들을 리스트에 잘 담아줍니다.

# set comprehension

list comprehension에서 대괄호를 중괄호로 바꾼다면 set comprehension이 됩니다.  
이는 따로 다루지는 않겠습니다.

# dict comprehension

set comprehension에서 key:value의 형태로 쓰게 되면 dict comprehension이 됩니다.  


```python
students = ['철수', '영희', '길동', '순희']
{student : 0 for student in students}
```




    {'길동': 0, '순희': 0, '영희': 0, '철수': 0}



딕셔너리의 key이름이 student고 그 student는 리스트 students의 요소인 것을 이렇게 for로 표현할 수 있습니다.  

key와 value를 둘 다 for로 돌려서 표현할 수 도 있습니다.  


```python
scores = {'철수': 50, '영희': 80, '길동': 90, '순희': 60, '전학생': 100}
## 전학생만 빼고 새로운 딕트를 만들고 싶으면
scores1 = { name: score for name, score in scores.items() if name != '전학생'}
scores
```




    {'길동': 90, '순희': 60, '영희': 80, '철수': 50}



name과 score이 딕트 scores1의 변수이고 두 변수는 원래 scores의 key와 value에서 가져온 것입니다.  
