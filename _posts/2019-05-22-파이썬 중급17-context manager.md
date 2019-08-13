---
layout : post
title : 파이썬 중급17-context manager
subtitle : 파이썬 중급17-context manager
category : 프로그래밍 언어 공부
tags : python
date : 2019-05-22 16:12:00
---

# 무엇?

위키백과에서 가져온 정의입니다.  

>Context management is a dynamic computer process that uses 'subjects' of data in one application, to point to data resident in a separate application also containing the same subject

쉽게 말하면 컴퓨터에서 활용할 수 있는 리소스는 제한적이므로 사용한 리소스는 종료해주는 것이 중요합니다.  
그래서 하나의 포인트(어플리케이션)에서 사용한 리소스가 있다면 그것을 꺼주는 것(관리해주는 것)을 context manager라고 합니다.  
아래의 코드를 한 번 보시죠.


```python
f = open('memo.txt', 'r')
print(f.read())
```

위의 코드만 실행을 시킨다면 memo.txt 파일은 열린채 컴퓨터에 남아있을 확률이 높습니다.  
따라서 아래와 같이 실행시켜 주어야 합니다.


```python
f = open('memo.txt', 'r')

try:
    ...

    print(f.read())

    ... (예외발생)

finally:
    f.close() # 예외가 발생하더라도 실행됨
```

이렇게 활용하면 마지막에 finally구문을 이용해서 종료시킬 수 있습니다.  
try구문을 굳이 쓰는 이유는 만약 에러가 발생더라도 파일은 자동으로 꺼지지 않기 때문입니다.  
따라서 예외처리를 통해서 리소스를 관리합니다.  
파이썬에서는 이것보다 더 간단한 with구문을 제공합니다.


```python
with open('memo.txt', 'r') as f:
    ...

    print(f.read())
```

이렇게 정의하면 에러가 생기거나 with문을 빠져나가면 자동으로 파일을 닫아준다.

# with구문을 쓸 수 있게 만드는 magic methods

magicmethods란 클래스의 \_\_init\_\_메소드와 같이 특정한 기능을 하도록 미리 설계된 메소드를 의미합니다.  
with구문을 사용하기 위해서는 클래스에 \_\_enter\_\_ 과 \_\_exit\_\_이라는 magic methods를 정희해주면 됩니다.  

- \_\_enter\_\_ : with구문에 진입하는 시점에 자동으로 호출되는 메소드  
- \_\_exit\_\_ : with구문을 빠져나오기 직전에 호출되는 메소드 type, value, traceback은 with문을 빠져나오기 전에 예외가 발생했을 때의 정보를 나타냄.

예제를 보겠습니다.  


```python
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker

class SQLAlchemyDBConnection(object):
    """SQLAlchemy database connection"""
    def __init__(self, connection_string):
        self.connection_string = connection_string
        self.session = None

    # with구문 진입시에 db와 connection을 하고
    # ORM을 사용하기 위한 session을 만들어준다.
    def __enter__(self):
        engine = create_engine(self.connection_string)
        Session = sessionmaker()
        self.session = Session(bind=engine)
        return self

    # with구문을 빠져나오기 전 session의 종료를 장한다.
    def __exit__(self, exc_type, exc_val, exc_tb):
        self.session.close()
```

 이렇게 클래스를 만들 때 \_\_enter\_\_와 \_\_exit\_\_를 매서드로 만들면 with구문과 함께 클래스를 사용할 수 있습니다.


```python
conn_str = 'mssql+pydobc://server_name/db_name?driver=SQL+Server'
db = SQLAlchemyDBConnection(conn_str)
with db:  ## with문과 함께 사용가능
    customer = db.session.query(Customer).filter_by(id=123).one()
    print(customer.name)
```

# contextmanager decorator

클래스로 정의하는 것 말고 contextmanager decorator를 사용할 수도 있습니다.  


```python
@contextmanager
def blahblah():
    a = ...
    return a
with blahblah as resource
```

이런식으로 함수위에 contextmanager decorator를 이용하면 with구문을 사용할 수 있습니다.  
