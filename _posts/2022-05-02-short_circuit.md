---
layout: single
title:  "[파이썬(Python)] 논리 연산식의 단락 (short circuit)"
categories: Python
tag: [Python, 파이썬, short circuit]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---





## 논리 연산식의 단락 (short circuit)
x >= 2 and ( x / y ) > 2 와 같은 논리 표현식을 파이썬에서 처리할 때, 왼쪽에서부터 오른쪽으로 표현식을 평가한다. and 정의 때문에 x 가 2 보다 작다면, x >= 2 는 거짓 (False) 으로, 전체적으로 ( x / y ) > 2 가 참 (True) 혹은 거짓 (False) 이냐에 관계없이 거짓 (False) 이 된다.

나머지 논리 표현식을 평가해도 나아지는 것이 없다고 파이썬이 자동으로 탐지할 때,평가를 멈추고 나머지 논리 표현식에 대한 연산도 중지한다. 최종값이 이미 결정되었기 때문에 더 이상의 논리 표현식의 평가가 멈출 때, 이를 단락 (short-citcuiting) 평가 라고 한다.

좋은 것처럼 보일 수 있지만, 단락 행동은 가디언 패턴 (guardian pattern) 으로 불리는 좀 더 똑똑한 기술로 연계된다. 다음 코드를 살펴보자.


```python
x = 6
y = 2
x >= 2 and (x / y) > 2
```




    True



x 가 2 보다 크거나 같으니, 왼쪽을 True. 6 / 2 = 3 이니 2 보다 크다. 따라서, 오른쪽도 True 이니, 둘 다 True 이다. 즉, 결과로 True 가 나온디.


```python
x = 1
y = 0
x >= 2 and (x / y) > 2
```




    False



이번에는 숫자를 바꾸었다. 여기서 우선 x 가 2 보다 크지 않기 때문에 뒤에 연산은 하지도 않고, 바로 False 가 된다. 사실 뒤에 y = 0 을 넣으면 분모에 0 이 들어가서 문제가 생길 것인데, 그건 무시하는 것이다. (이것이 단락 평가 규칙에 의한 것으로 뒤에 연산이 필요 없으면 안하는 것이다.)


```python
x = 6
y = 0
x >= 2 and (x / y) > 2
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-4-1150670be796> in <module>
          1 x = 6
          2 y = 0
    ----> 3 x >= 2 and (x / y) > 2
    

    ZeroDivisionError: division by zero


위와 같이 x 를 2 보다 큰 6 을 넣게 되면, 예상할 수 있듯이, 0 으로 나누었다고 문제를 발생시킨다. 평가 오류가 발생하기 전에 가디언 평가식을 전략적으로 배치해서 논리 표현식을 다음과 같이 구성한다.


```python
x = 6
y = 0
x >= 2 and y != 0 and (x / y) > 2
```




    False



위와 같이 y != 0 라고 하는 연산을 추가하는데, y 가 0 이 아니라는 가디언 평가를 넣어 주면, y 가 0 이 아니라는 것을 확인하고, 진행을 하게 된다. 그러면, y 가 0 이 되면 에러가 아닌 False 가 되도록 세팅하는 것이다. 그런데 만약에 순서를 살짝 이동하면 어떻게 될까?


```python
x = 6
y = 0
x >= 2 and (x / y) > 2 and y != 0
```


    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-7-a54ea65c3436> in <module>
          1 x = 6
          2 y = 0
    ----> 3 x >= 2 and (x / y) > 2 and y != 0
    

    ZeroDivisionError: division by zero


위의 경우, 먼저 x / y 를 평가하므로, y 가 0 인 것이 들어가서 평가를 하게 된다. 그래서 동일한 에러가 발생한다. 따라서, y 가 0 이 아닐 때만 (x / y ) 가 실행하도록 y != 0 이  바로 앞의 코드의 경우에 가디언 역할을 수행한다고 말할 수 있다.
