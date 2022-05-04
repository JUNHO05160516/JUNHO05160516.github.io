---
layout: single
title:  "[파이썬(Python)] 매개 변수 (parameter)와 인수 (argument)"
categories: Python
tag: [Python, 파이썬, parameter, argument]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---


## 매개 변수 (parameter)와 인수 (argument)
몇몇 내장 함수는 인자를 요구한다. 예를 들어, math.sin() 함수를 호출할 때, 숫자를 인자로 넘겨야 한다. 어떤 함수는 2개 이상의 인수를 받는다. math.pow() 는 밑과 지수 2개의 인자가 필요하다.

인자는 함수 내부에서 매개 변수 (parameters) 로 불리는 변수로 대입된다. 하나의 인자를 받는 사용자 정의 함수 (user-defined function) 가 예제로 있다.


```python
def print_twice(bruce):
    print(bruce)
    print(bruce)
```

사용자 정의 함수는 인자를 받아 매개변수 bruce에 대입한다. 함수가 호출될 때, 매개 변수의 값 (무엇이든 관계 없이)을 두 번 출력한다.

사용자 정의 함수는 출력 가능한 임의의 값에 작동한다.


```python
print_twice('Spam')
```

    Spam
    Spam
    


```python
print_twice(17)
```

    17
    17
    

위와 같이 문자열이나 숫자도 가능하고, 아래와 같이 특정 모듈에 있는 변수 값도 가능하다.


```python
import math
print_twice(math.pi)
```

    3.141592653589793
    3.141592653589793
    

내장함수에 적용되는 동일한 구성 규칙이 사용자 정의 함수에도 적용되어서 print_twice 함수 인자로 표현식 어떤 종류도 가능하다.


```python
print_twice('Spam ' *4)
```

    Spam Spam Spam Spam 
    Spam Spam Spam Spam 
    


```python
print_twice(math.cos(math.pi))
```

    -1.0
    -1.0
    

함수가 호출되기 전에 인자에 대한 평가는 완료되어, 예제에서 'Spam ' * 4 와 math.cos(math.pi) 는 단지 1회만 평가된다.

변수도 인자로 사용이 가능하다.


```python
michael = 'Eric, the half a bee'
print_twice(michael)
```

    Eric, the half a bee
    Eric, the half a bee
    

위와 같이 인수자 넘기는 변수명 (michael) 은 매개 변수명 (bruce) 과 아무런 연관이 없다. 무슨 값이 호출 되든지 호출하는 측과 상관이 없다. 여기 print_twice() 함수에는 누구나 bruce 라고 부르면 되는 것이다.
