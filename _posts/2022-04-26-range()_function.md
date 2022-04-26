---
layout: single
title:  "[파이썬(Python)] range() 함수"
categories: Python
tag: [Python, 파이썬, range()]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---



## [파이썬(Python)] range() 함수
range() 함수는 증가하는 리스트를 생성해주는 함수이다.

### range(a,b,c) <br/>
: a(시작 값), b(b-1이 마지막 값), c(간격) <br/>
: a에서 시작해서 b-1 까지 c 만큼 증가하는 시퀀스를 리스트로 나열한다.

### range(a,b) <br/>
: a(시작 값), b(b-1이 마지막 값) <br/>
: a에서 시작해서 b-1 까지 1 만큼 증가하는 시퀀스를 리스트로 나열한다.

### range(a) <br/>
: a(a-1이 마지막 값) <br/>
: 0에서 시작해서 a-1 까지 1 만큼 증가하는 시퀀스를 리스트로 나열한다.


```python
print(list(range(1,9,2)))
```

    [1, 3, 5, 7]
    


```python
print(list(range(1,9)))
```

    [1, 2, 3, 4, 5, 6, 7, 8]
    


```python
print(list(range(9)))
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8]
    

(1, 9, 2) 를 입력하면 1 부터 8 까지 2 의 간격으로 증가시키는데, 1 에서 2 를 증가 시키면 3 이고, 7 에서 2 를 증가시키면 9 인데 범위 밖이다. 따라서 9 는 나타내지 않는다.

(1, 9) 를 입력하면 2 부터 8 까지 1 의 간격으로 증가시킨 리스트를 생성한다는 것을 확인할 수 있다.

(9) 를 입력하면 0 부터 8 까지 1 씩 증가하는 리스트가 생성됨을 확인할 수 있다.
