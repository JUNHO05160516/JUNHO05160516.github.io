---
layout: single
title:  "[파이썬(Python)] 변수 갱신 연습"
categories: Python
tag: [Python, 파이썬, variable, 변수]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---







## 변수 갱신 연습
흔한 패턴은 변수를 갱신하는 대입문이다. 변수의 새로운 값은 이전 값에 의존한다.


```python
x = x + 1
```


    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-2-2d25c2ef041b> in <module>
    ----> 1 x = x + 1
    

    NameError: name 'x' is not defined


위의 경우, "현재 값 x 에 1 을 더해서 x 를 새로운 값으로 갱신한다." 라는 의미이다. 만약 존재하지 않는 변수를 갱신하면 오류가 생긴다. 왜냐하면 x 에 값을 대입하기 전에 파이썬이 오른쪽을 먼저 평가하기 때문이다.

변수를 갱신하기 전에 간단한 변수 대입으로 통산 먼저 초기화 (initialize) 를 한다.


```python
x = 0
x = x + 1
print(x)
```

    1
    

1 을 더해서 변수를 갱신하는 것을 증가 (increment) 라고 하고, 1 을 빼서 변수를 갱신하는 것을 감소 (decrement) 라고 한다. 
