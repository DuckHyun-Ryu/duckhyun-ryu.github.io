---
layout : post
title : 파이썬 중급12-collections(namedtuple)
subtitle : 파이썬 중급12-collections(namedtuple)
category : 프로그래밍 언어 공부
tags : python
date : 2019-05-22 10:23:00
---

# 무엇?

이름에서 알 수 있듯이 인덱스로만 접근할 수 있는 tuple과는 다르게 key값으로 접근가능하도록 제공하는 tuple이다.

# 사용법


```python
nametuple(typename, filed_names, verbose = False, rename = False)
```

field_name을 통해서 nametule()의 키를 정의할 수 있습니다.  
field_name은 공백이나 콤마를 이용해서 구분하거나 혹은 리스트 안에 넣어서 인자를 설정해주어야 합니다.  


주의할 점은 nametupe 매서드는 어떤 자료형을 만드는 것이 아니라 typename에 따라 새로운 type을 설정한다는 것입니다.    
type이라하면 tuple이나 list들을 type이라 하는데 새로운 type을 하나 설정을 하는 것이라 볼 수 있습니다.  
예제를 보겠습니다.  


```python
from collections import namedtuple
Person =namedtuple("Person", 'name age gender')
type(Person)
```




    type



type함수를 쓴 결과를 보시면 Person자체가 type이라는 것을 알 수 있습니다.  
여기서 이제 Person type의 변수들을 지정해 보도록 하겠습니다.


```python
P1 = Person(name = 'Jhon', age  =28, gender = '남')
P1
```




    Person(name='Jhon', age=28, gender='남')



P1이라는 변수는 Person자료형으로 정의된 것입니다.  

# 다양한 매서드들

### _asdict()

기존에 생성된 namedtuple()의 인스턴스(객체)fmf OrderedDIct로 변환해주는 함수이다.  


```python
Person  = namedtuple('Person', 'name age gender')
P1 = Person('Tom',24, '남' )
P1._asdict() ## asdict 사용
```




    OrderedDict([('name', 'Tom'), ('age', 24), ('gender', '남')])



### _replace(kwargs)

기존에 생성된 namedtuple()의 인스턴스(객체)의 값을 변경할 때 사용하는 함수이다.  


```python
Person  = namedtuple('Person', 'name age gender')
P1 = Person('Tom',24, '남' )
P1 = P1._replace(name = 'Neo')
P1 = P1._replace(age = 27)
P1 = P1._replace(gender = '여')
P1
## inplace가 안되므로 새로 지정해 주어야한다.
```




    Person(name='Neo', age=27, gender='여')



### _fields

생성된 namedtuple()의 필드명을 tuple형식으로 return한다.  


```python
Person  = namedtuple('Person', 'name age gender')
P1 = Person('Tom',24, '남' )
P1._fields
```




    ('name', 'age', 'gender')



### getattr()

getattr은 namedtuple()의 메소드는 아니지만, field_names로 namedtuple()의 인스턴스(객체)의 값을 추출해준다.  


```python
Person  = namedtuple('Person', 'name age gender')
P1 = Person('Tom',24, '남' )
getattr(P1, 'name') ##name field의 값을 추출해라
```




    'Tom'



### dict에서 namedtuple로 변환할 때 **

**는 dict를 namedtyple()로 변환해준다.


```python
Person  = namedtuple('Person', 'name age gender')
dic = {'name':'Tom', 'age': 24, 'gender' : '남'}
P2 = Person(**dic)
P2
```




    Person(name='Tom', age=24, gender='남')
