---
layout: single
title:  "[파이썬(Python)] 함수 호출과 내장 (Built-in) 함수"
categories: Python
tag: [Python, 파이썬, function call, built-in]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---



## 함수 호출과 내장 (Built-in) 함수

* 함수 호출

프로그래밍 문맥에서, 함수 (function) 는 연산을 수행하는 명명된 일련의 문장이다. 함수를 정의할 때, 이름과 일련된 문장을 명기한다. 나중에, 함수를 이름으로 '호출 (call)' 한다. 이미 함수 호출 (function call) 의 예제를 다루어보았다.


```python
type(32)
```




    int



아주 단순하지만, 위의 함수는 type() 이다. 괄호안의 표현식을 함수의 인자 (argument) 라고 한다. 인자는 함수 입력으로 함수 내부로 전달되는 값이나 변수이다. 앞선 type 함수에 대한 결과는 인자의 자료형 (type) 이다.

통상 함수가 인자를 '받아' 결과를 '반환' 한다. 결과를 결과값 (return value) 라고 부른다.

* 내장 (Built-in) 함수

함수를 정의할 필요 없이 사용할 수 있는 내장함수가 파이썬에는 많다. 공통의 문제를 해결할 수 있는 함수를 파이썬 창시자 (Guido van Rossum) 가 작성해서 누구나 사용할 수 있도록 파이썬에 포함했다.


```python
max('Hello world')
```




    'w'




```python
min('Hello world')
```




    ' '



max() 함수는 문자열의 '가장 큰 문자', 위 예제에서 'w', min() 함수는 최소 문자를, 위 예제에서는 공백을 출력한다.

매우 자주 사용되는 또 다른 내장 함수는 얼마나 많은 항목이 있는지 출력하는 len() 함수가 있다. 만약 len() 함수의 인수가 문자열이면 문자열에 있는 문자 개수를 반환한다.


```python
len('Hello world')
```




    11



이들 함수는 문자열에만 국한된 것이 아니라, 다양한 자료형에 사용된다. 내장함수 이름은 사전에 점유된 예약어로 취급해야 한다. 예를 들어 'max' 를 변수명으로 사용하지 말아야 한다.
