---
layout: single
title:  "[파이썬(Python)] startswith() 함수"
categories: Python
tag: [Python, 파이썬, startswith()]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---


## startswith() 함수

문자열 데이터에 startswith() 함수를 적용할 수 있다. 대상 문자열이 어떤 문자로 시작하는지 확인해 준다. 특정한 문자로 시작하는 문자열을 찾거나, 제거할 때 주로 유용하게 사용할 수 있다.


```python
'abcde'.startswith('b')
```




    False




```python
'abcde'.startswith('ab')
```




    True
