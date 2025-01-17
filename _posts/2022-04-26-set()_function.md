---
layout: single
title:  "[파이썬(Python)] set() 함수"
categories: Python
tag: [Python, 파이썬, set(), list(set())]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---

## set() 함수
set() 함수를 사용하면 중복되는 값들을 제거해주고, 대표되는 한 문자만 살린다. 본래 가지고 있던 순서는 없어지고, sorted 를 수행해서 정렬을 하게 된다.


```python
set('FFFABBBCDDDDEDED')
```




    {'A', 'B', 'C', 'D', 'E', 'F'}




```python
set('957348915-423refasfr23423ds')
```




    {'-', '1', '2', '3', '4', '5', '7', '8', '9', 'a', 'd', 'e', 'f', 'r', 's'}



하지만, 이것을 리스트로 만들게 되면 순서가 없어지고 지맘대로 나열한다.


```python
list(set('FFFABBBCDDDDEDED'))
```




    ['B', 'C', 'D', 'A', 'F', 'E']




```python
list(set('957348915-423refasfr23423ds'))
```




    ['e', '5', 'a', '2', '8', '-', 's', 'f', 'd', '3', '7', 'r', '4', '1', '9']



맨 위에는 F 로 시작하는 문자열의 경우, 반복을 모두 제거하고, ABCD... 순으로 정렬을 해준 것을 보여준다. 숫자를 넣어도 동일하며, 특수 문자가 앞으로 오고, 숫자가 그다음, 문자가 숫자 뒤로 가는 것 같다. 특정 순서를 사용할 때는 set 자체를 사용하고, list() 함수가 적용되었을 때에는 순서는 램덤이라는 점을 명심하자.
