---
layout : post
title : 파이썬 중급 1- args와 kwargs
subtitle : 파이썬 중급 1- args와 kwargs
category : 프로그래밍 언어 공부
tags : python
date : 2019-05-20 15:18:01
---

# 무엇?

\*args와 \*\*kwargs는 함수를 정의할 때와 호출할 때 사용됩니다.  
\*args와 \*kwargs는 가변 갯수인 매개변수 입니다.
가변 갯수란 사용자가 함수의 인자로 몇 개를 넣을지 모른다는 뜻입니다.   
여기서 주의할 점은 굳이 \*args, \*\*kwargs라고 쓰지 않아도 됩니다.  
\*var 혹은 \*\*vars라고 써도 됩니다.  
즉, \* 와 \*\*만 넣어준다면 어떤 변수명을 써도 상관이 없습니다.  

# 함수를 정의 할 때 사용법

## *args


```python
def test_var_args(f_arg, *argv):
    print('첫 번째 인자:', f_arg)
    for arg in argv:
        print('*argv의 다른인자', arg)

test_var_args('야숩', 'python ', '달걀', 'test')
```

    첫 번째 인자: 야숩
    *argv의 다른인자 python
    *argv의 다른인자 달걀
    *argv의 다른인자 test


위의 결과를 보면 야숩의 f_arg의 변수로 야숩이 들어왔고 나머지 python, 달걀, test는 \*argv 매개변수의 것 입니다.  
이렇게 몇 개의 인자가 들어올지 모를 때 사용하는 것이 \*args입니다.

## **kwargs의 사용법

\*\*kwargs는 키워드화 된 가변 갯수의 인자들을 함수에 보낼 때 사용합니다.  
dict가 가장 많이 쓰이는 예 중 하나입니다.


```python
def greet_me(**kwargs):
    if kwargs is not None:
        for key, value in kwargs.items():
            print ("%s == %s" % (key, value))
greet_me(name = 'yasoob', nickname = 'goldcuking')

```

    nickname == goldcuking
    name == yasoob


이렇게 가변 갯수이긴 한데 그 변수가 키워드화 된 변수일 때 **kwargs를 사용합니다.

## 함수를 호출할 때의  \*args와 \**kwargs

일단 *args변수가 아닌  정의하자 형식 인자(format args)로 함수를 하나 정의하자 정의하자


```python
def test_args_kwargs(arg1, arg2, arg3):
        print ("인자1:", arg1)
        print ("인자2:", arg2)
        print ("인자3:", arg3)

```

그리고 튜플 a와 딕트 b를 정의하자


```python
a = ('two', 3,5)
b = {'인자3:': 3, '인자2:': 'two', '인자1:':5}
```

이 때 a와 b안에 있는 인자들을 test_args_kwargs에 넣고 싶을 때 인덱싱을 써서 넣는게 아닌 바로 넣을 수 있다.  


```python
test_args_kwargs(*a)
```

    인자1: two
    인자2: 3
    인자3: 5



```python
test_args_kwargs(**b)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-17-fa086c94f831> in <module>
    ----> 1 test_args_kwargs(**b)


    TypeError: test_args_kwargs() got an unexpected keyword argument '인자2:'


### \*arg, \**kwargs 형식인자(format args)의 사용순서

위의 형식인자는 우리가 기본적으로 함수에 사용하는 매개변수이다.  
3가지를 동시에 사용할 때는 꼭 밑의 순서를 지켜주어야 한다.  


```python
some_func(fargs, *args, **kwargs)
```

# 언제 사용하나요??
