---
layout : post
title : 파이썬 중급 9- collection(OrderedDict)
subtitle : 파이썬 중급 9- collection(OrderedDict)
category : 프로그래밍 언어 공부
tags : python
date : 2019-05-21 15:52:00
---

# 무엇?

dict를 정의하면 순서가 정해져 있지 않습니다.   
예를 들어보겠습니다.  


```python
colours =  {"빨강" : 198, "녹색" : 170, "파랑" : 160}
for key, value in colours.items():
    print(key, value)
```

    파랑 160
    빨강 198
    녹색 170


결과값을 보면 정의한 빨강, 녹색, 파랑 순이 아닌 파랑 빨강, 녹색 순으로 나오는 것을 알 수 있습니다.  
만약 이 순서를 지키고 싶을 때 사용할 수 있는 것이 Ordereddict입니다.  


```python
from collections import OrderedDict

colours = OrderedDict([("빨강", 198), ("녹색", 170), ("파랑", 160)])
for key, value in colours.items():
    print(key, value)
```

    빨강 198
    녹색 170
    파랑 160


dict 대신에 OrderedDict로 정의하면 순서를 지킬 수 있다.  
