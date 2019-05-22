
---
layout : post
title : 파이썬 중급10-collection(Counter)
subtitle : 파이썬 중급10-collection(Counter)
category : 프로그래밍 언어 공부
tags : python
date : 2019-05-21 15:57:00
---

# 무엇?

컨테이너에 동일한 값의 자료가 몇개인지를 파악하는데 사용하는 객체이다. Counter() 함수의 인자는 컨테이너 자료형이면 모두 가능하다.  

인자의 자료형에 따라 Counter 함수를 사용해보자. 

## list와 string


```python
## list 
from collections import Counter 

lst = ['aa','cc','d','e','f','d']
print(Counter(lst))
```

    Counter({'d': 2, 'f': 1, 'aa': 1, 'e': 1, 'cc': 1})
    

이렇게 lst의 요소들을 키로 하고 갯수를 value로 하는 딕셔너리 형태로 결과값이 출력된다.  
문자열도 가능하다.  


```python
## 문자열
a = 'aabcdeffgg'
print(Counter(a))
```

    Counter({'a': 2, 'f': 2, 'g': 2, 'c': 1, 'e': 1, 'b': 1, 'd': 1})
    

이렇게 문자열에서도 알파벳이 몇 개가 쓰였는지 내림차순으로 알려준다. 

## 딕셔너리와 값 = 개수 형태 

딕셔너리와 '값 = '개수 형태'의 인자가 들어가게 되면 얘기가 좀 더 달라집니다.  
딕셔너리 같은 경우 key가 세어지는 주체가 되고 value를 갯수로 취급합니다.   
코드를 통해서 확인해 보겠습니다.  


```python
## dictionary
from collections import Counter
a  = {'가': 3, '나': 2, '다': 4}
print(Counter(a))
```

    Counter({'다': 4, '가': 3, '나': 2})
    

결과값을 보면 그냥 '다'의 갯수는 a의 '다'의 value 값과 같습니다.  

'값= 갯수' 형태도 마찬가지 입니다.  


```python
## 값 = 갯수
from collections import Counter
print(Counter(a = 3, b = 1))
```

    Counter({'a': 3, 'b': 1})
    

Counter 함수에 직접 a = 3, b = 1을 집어넣으면 a가 3개 b는 1개라고 생각하는 것입니다.  

# 다양한 매서드

### update

Counter의 값을 수정할 때 사용합니다.  


```python
# 문자열
a = Counter()
print(a)
a.update("abcdefg")
print(a)

# 딕셔너리
a.update({'f':3, 'e':2})
print(a)
```

    Counter()
    Counter({'c': 1, 'e': 1, 'b': 1, 'a': 1, 'f': 1, 'd': 1, 'g': 1})
    Counter({'f': 4, 'e': 3, 'c': 1, 'b': 1, 'a': 1, 'd': 1, 'g': 1})
    

a라는 Counter 객체에 문자열을 넣은 후 다시 딕셔너리를 넣으면 딕셔너리의 값을 반영해서 도출된다. 

### elements

주체 : 갯수로 표시된 것을 풀어서 나타내주는 매서드  
이것 또한 예제로서 살펴보자 


```python
c = Counter(a=2, b=3, c=2)
print(Counter(c))
print(list(c.elements()))
```

    Counter({'b': 3, 'c': 2, 'a': 2})
    ['c', 'c', 'b', 'b', 'b', 'a', 'a']
    

이렇게 갯수를 출력하는 것이 아닌 실제로 2개씩 출력이 된다.  
element 또한 주소값만을 의미하므로 list나 for을 이용하여 값을 출력할 수 있다.

### most_commnon(n)

갯수가 n개인 것들만 tuple로 알려준다.  
만약에 괄호 안에 아무것도 들어있지 않으면 모든 요소들이 갯수와 함께 튜플로 나오게 되는데 이 때 갯수가 내림차순으로 정렬된다.  


```python
c2 = Counter('apple , orange, grape')
print(c2.most_common()) ## 아무것도 들어있지 않을 때
```

    [(' ', 3), ('e', 3), ('a', 3), ('p', 3), ('r', 2), ('g', 2), (',', 2), ('l', 1), ('o', 1), ('n', 1)]
    


```python
print(c2.most_common(3)) ## 갯수가 3인 알파벳만 출력
```

    [(' ', 3), ('e', 3), ('a', 3)]
    

### subtract()

요소를 빼는 것을 의미합니다.  
만약 'hello python'에서 'i love python'을 빼주면 l이 2개에서 1개로 줄어드는 것입니다.  
다만 v와 i는 hello python에 없으므로 음수 -1이 나오게 됩니다.  
예제를 통해서 보겠습니다.  


```python
c3 = Counter('hellow python')
c4 = Counter('i love pytho')
c3.subtract(c4) ## c3에서 c4요소를 빼겠다는 의미  
print(c3)
```

    Counter({'l': 1, 'w': 1, 'h': 1, 'n': 1, 't': 0, 'p': 0, 'y': 0, 'e': 0, 'o': 0, ' ': -1, 'i': -1, 'v': -1})
    

결과를 보면 공백과 i,v는 -1이 나타나는 것을 볼 수 있다. 
만약 한 번 더 한다면? 그러면 -2가 나올 것이다.  

# Counter를 이용한 연산


### 연산
Counter은 산술/집합 연산이 가능합니다.  
더하기, 빼기 , 교집합, 합집합의 연산이 가능합니다.  

### 더하기&빼기


```python
# 더하기
a = Counter([1,2,3,4,5])
b = Counter([6,5,2,3,1])
a+b
```




    Counter({1: 2, 2: 2, 3: 2, 4: 1, 5: 2, 6: 1})




```python
# 빼기
a- b
```




    Counter({4: 1})



빼기에서는 subtract와 다르게 음수가 나타나지 않는다.  

### 교집합&합집합


```python
## 교집합
a&b
```




    Counter({1: 1, 2: 1, 3: 1, 5: 1})




```python
##합집합
a|b
```




    Counter({1: 1, 2: 1, 3: 1, 4: 1, 5: 1, 6: 1})


