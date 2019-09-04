---
layout : post
title : 4828. \[파이썬 S/W 문제해결 기본\] 1일차 - min max
subtitle : 4828. \[파이썬 S/W 문제해결 기본\] 1일차 - min max
category : practice coding
tags : python
date : 2019-09-03 12:34:00
---


## 문제

N개의 양의 정수에서 가장 큰 수와 가장 작은 수의 차이를 출력하시오.


[입력]

첫 줄에 테스트 케이스의 수 T가 주어진다. ( 1 ≤ T ≤ 50 )

각 케이스의 첫 줄에 양수의 개수 N이 주어진다. ( 5 ≤ N ≤ 1000 )

다음 줄에 N개의 양수 ai가 주어진다. ( 1 ≤ ai≤ 1000000 )

[출력]

각 줄마다 "#T" (T는 테스트 케이스 번호)를 출력한 뒤, 답을 출력한다.

## 해결


```python
T = int(input())
for i in range(T):
    num = int(input())
    arr = list(map(int, input().split()))
    N = max(arr)
    M = min(arr)
    print('#{0} {1}'.format(i+1, N-M))
```
