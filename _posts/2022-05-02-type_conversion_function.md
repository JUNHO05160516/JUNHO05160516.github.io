---
layout: single
title:  "[파이썬(Python)] 자료형 (type) 변환 함수"
categories: Python
tag: [Python, 파이썬, type()]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---


## 자료형 (type) 변환 함수
파이썬에는 이런 자료형 (type) 에서 저런 자료형으로 값을 변환하는 내장 함수가 있다. int() 함수는 임의의 값을 입력 받아 변환이 가능하면 정수형으로 변환하고, 그렇지 않으면 오류가 발생한다.


```python
int('32')
```




    32



위와 같이 32 라는 값을 '' 를 사용해서 문자로 쓸 수 있지만, 이걸 int() 함수의 인자로 넣어서 정수값으로 변환할 수 있다.


```python
int('Hello')
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-2-6765ce49acfe> in <module>
    ----> 1 int('Hello')
    

    ValueError: invalid literal for int() with base 10: 'Hello'


하지만, 위와 같이 Hello 라는 문자를 int() 함수의 인자로 넣게 되면, 정수가 될 수 없는 문자이기 때문에 오류를 보야준다.

또한, 아래와 같이 부동 소수점 값은 정수로 변환이 ㅏ능하며, 소수점 이하를 절삭한다.


```python
int(3.9999)
```




    3



음수의 보동 소수점의 경우에도 마찬가지다.


```python
int(-2.3)
```




    -2




```python
float(32)
```




    32.0




```python
float('3.14')
```




    3.14



float() 함수를 사용하면 정수와 문자열을 부동 소수점으로 변환한다.

마지막으로 str() 함수를 사용하면 인자를 문자열로 변환한다.


```python
str(32)
```




    '32'




```python
str(3.14159)
```




    '3.14159'


