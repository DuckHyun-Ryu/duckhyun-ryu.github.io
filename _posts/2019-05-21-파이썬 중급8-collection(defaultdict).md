---
layout : post
title : 파이썬 중급 8-collection(defaultdict)
subtitle : 파이썬 중급 8-collection(defaultdict)
category : 프로그래밍 언어 공부
tags : python
date : 2019-05-21 13:57:00
---

# 무엇?

파이썬 collection은 컨테이너 데이터 타입들이 다수 포함된 모듈들을 제공하는 패키지 입니다.  
우리가 살펴볼 모듈은 아래와 같습니다.  
- defaultdict  
- counter  
- deque  
- namedtuple  
- enum.Enum(모듈 외부, 파이썬 3.4이상)

# defaultdict

dict와 유사한 defaultdict의 가장 dict와 가장 큰 차이점은 없는 지정되지 않은 key를 호출하면 해당 key의 value가 사용자가 설정한 자료형의 값으로 나오게 됩니다.
예를 하나 들어보겠습니다.


```python
from collections import defaultdict
int_dict = defaultdict(int)
int_dict
```




    defaultdict(int, {})



defaultdict의 기본값을 int로 설정을 하였습니다.  
여기서 없는 key를 한 번 불러 보겠습니다.  


```python
int_dict['key1']
```




    0



보시면 key1라는 key는 없음에도 불구하고 0이라는 값이 디폴트로 들어가 있는 것이 dict와 가장 큰 차이점입니다.  
set과 list로 할 수도 있습니다.  


```python
list_dict = defaultdict(list)
list_dict['key1']
```




    []




```python
set_dict = defaultdict(set)
set_dict['key1']
```




    set()



# 언제 사용할까?

- 문자열에 나타난 알파벳의 횟수를 계산하는 예제(int)


```python
letters = 'dongdongfather'
letters_dict = defaultdict(int)
for k in letters:
    letters_dict[k] +=1
letters_dict
```




    defaultdict(int,
                {'a': 1,
                 'd': 2,
                 'e': 1,
                 'f': 1,
                 'g': 2,
                 'h': 1,
                 'n': 2,
                 'o': 2,
                 'r': 1,
                 't': 1})



letters의 알파벳이 몇 개씩 있는지 알고 싶은데 빈 dict를 쓰게 되면  
없는 key가 있는 경우 에러가 발생한다.  
하지만 defaultdict를 사용할 경우 그럴 걱정을 하지 않고 사용할 수 있다.  

- default가 list일 때 활용예제


```python
name_list = [('kim','sungsu'), ('kang','hodong'), ('park','jisung'), ('kim','yuna'), ('park','chanho')]
ndict = defaultdict(list)

name_list = [('kim','sungsu'), ('kang','hodong'), ('park','jisung'), ('kim','yuna'), ('park','chanho'), ('kang','hodong')]
for k,v in name_list:
    ndict[k].append(v)
ndict
```




    defaultdict(list,
                {'kang': ['hodong', 'hodong'],
                 'kim': ['sungsu', 'yuna'],
                 'park': ['jisung', 'chanho']})



예제를 보면 name_list에 성과 이름이 튜플로 저장되어 있다.  
이 때 같은 성을 가진 사람들끼리 묶고 싶을 때 생각없이 ndict의 key값을 따로 설정해 줄 필요가 없다.  
그리고 만약에 key가 설정이 되어 있다면 이제 해당 key로 다시 접근을 하므로 위와 같이 결과값이 나오게 된다.  

그런데 결과값을 보면 hodong이 지금 2번 중복되어서 나와 있다.  
이 때 해결할 수 있는 것이 set이다.


```python
name_list = [('kim','sungsu'), ('kang','hodong'), ('park','jisung'), ('kim','yuna'), ('park','chanho')]
nset = defaultdict(set)

name_list = [('kim','sungsu'), ('kang','hodong'), ('park','jisung'), ('kim','yuna'), ('park','chanho'), ('kang','hodong')]
for k,v in name_list:
    nset[k].add(v)
nset
```




    defaultdict(set,
                {'kang': {'hodong'},
                 'kim': {'sungsu', 'yuna'},
                 'park': {'chanho', 'jisung'}})



요렇게 해주면 hodong의 중복을 방지할 수 있다.  
