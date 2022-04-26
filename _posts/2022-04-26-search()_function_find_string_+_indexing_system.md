---
layout: single
title:  "[파이썬(Python)] search() 함수: 문자열 찾기! + 인덱싱 시스템"
categories: Python
tag: [Python, 파이썬, re.search(), search, index]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---


## search() 함수: 문자열 찾기! + 인덱싱 시스템
search() 함수를 사용하기 위해서는 re 를 먼저 import 한다. 원하는 문자의 인덱스를 찾아낼 수 있다.

re.search() 함수를 사용해서 문자열의 인덱스를 찾아보자. 여기서 주의할 점은 re.search) 함수는 첫 번째 인자가 찾고자 하는 패턴이며, 두 번째 인자가 대상이 되는 영역이다. 위의 예시에는 'TA'는 내가 찾고자 하는 패턴, 'attTA' 가 훝어 볼 문자열이다. TA 라는 패턴은 attTA에서 네 번째에 처음 시작하게 된다. 파이썬은 0 부터 ㅣ작하기 때문에 3 을 출력한다. 패턴이 처음 시작하는 위치를 잡아내기 위해서는 뒤에 .start() 함수를 적용시켜줘야 한다.


```python
import re

print( re.search('TA', 'attTA').start())
```

    3
    


```python
print( re.search('TA', 'attTA').end())
```

    5
    

반대로 패턴이 끝나는 부분에서의 인자를 찾고자 한다면 뒤에 .end() 함수를 적용시켜 줘야 한다. 따라서, 맨 마지막인 다섯 번째이다. 아래는 이해를 돕기 위해 적었다.

만약 ABCDE가 있다면 인덱싱은 0 A 1 B 2 C 3 D 4 E 5 이다. 하나의 인덱싱이 있다기 보다 살짝 비껴서 있다. 즉, ABCDE 라는 문자열이 있을 때, BC 를 출력하고 싶으면 1 에서 2 라고 인덱스를 가져 오는 것이 아니라, 1 에서 3 이라고 해야 그 사이에 있는 BC 가 걸려서 출력되는 것이다.


```python
x = 'ABCDE'
x[1:3]
```




    'BC'




```python
x[1:2]
```




    'B'


