---
layout : post
title : 파이썬중급11-collections(deque)
subtitle : 파이썬중급11-collections(deque)
category : 프로그래밍 언어 공부
tags : python
date : 2019-05-22 10:01:00
---

# 무엇?

deque는 double_ended queue의 줄임말로, 앞과 뒤에서 데이터를 처리할 수 있는 queue형 자료구조를 의미한다.  

![20190522_100314.png](attachment:20190522_100314.png)

# 사용법

deque의 인자로는 여러 컨테이너 타입의 자료형으로 받으면 된다.


```python
from collections import deque
deq  =deque([1,2,3])
```

# 여러가지 매서드들

## -append(x)

리스트와 마찬가지로 deque의 오른쪽(마지막)에 x를 추가해준다.


```python
eq =deque(['a', 'b', 'c'])
deq.append('d')
print(deq)
```

    deque([1, 2, 3, 'd'])


## -appendleft(x)

deque는 양방향에서 데이터를 처리할 수 있는 구죄므로 appendleft는 왼쪽에서 x를 추가해주는 함수이다.  


```python
deq = deque(['a', 'b', 'c'])
deq.appendleft('d')
print(deq)
```

    deque(['d', 'a', 'b', 'c'])


## - extend(x)

마찬가지로 마지막(오른쪽)에 요소를 추가해주는 함수이다.  
append와 extend의 차이는 파이썬 기본에서 다루었다.  


```python
deq =deque(['a', 'b', 'c'])
deq.extend('d')
print(deq)
```

    deque(['a', 'b', 'c', 'd'])


## - extendleft(x)

appendleft와 마찬가지로 왼쪽에 요소를 추가할 수 있는 함수이다.  


```python
deq = deque(['a', 'b', 'c'])
deq.extendleft('de')
print(deq)
```

    deque(['e', 'd', 'a', 'b', 'c'])


## - pop()

리스트와 마찬가지로 오른쪽(마지막)에서 부터 차례대로 제거 후 반환하는 메소드 이다.   


```python
deq = deque(['a', 'b', 'c'])
print('deque.pop() ->', end=' ')
while True:

    try: ## 마지막 요소가 없을 때 에러가 나지 않기 위한 try-except구문
        print(deq.pop(), end=' ')
    except IndexError:
        break
```

    deque.pop() -> c b a

## - popleft()

양방향 처리 자료구조라는 이름에 걸맞게 왼쪽에서 제거와 반환을 하는 함수이다.  


```python
deq =deque(['a', 'b', 'c'])
print('deque.popleft() ->', end=' ')
while True:
    try:
        print(deq.popleft(), end=' ')
    except IndexError:
        break
```

    deque.popleft() -> a b c

## - rotate(n)

요소들을 n의 값만큼 밀어주는 함수입니다.  
예를 들어 [1,2,3]을 1만큼 민다는 뜻은 [3,1,2]가 된다는 뜻입니다.
n이 만약 음수이면 왼쪽으로 밀어줍니다.  


```python
# 1만큼 오른쪽으로 밀었을 때
deq = deque(['a', 'b', 'c', 'd', 'e'])
deq.rotate(1)
deq
```




    deque(['e', 'a', 'b', 'c', 'd'])




```python
# 1만큼 왼쪽으로 밀엇을 때
deq = deque(['a', 'b', 'c', 'd', 'e'])
deq.rotate(-1)
deq
```




    deque(['b', 'c', 'd', 'e', 'a'])
