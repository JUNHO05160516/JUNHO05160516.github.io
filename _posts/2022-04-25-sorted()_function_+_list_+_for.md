---
layout: single
title:  "[파이썬(Python)] sorted 함수 + list 내부에서 반복문 작성 연습"
categories: Python
tag: [Python, 파이썬, sorted(), for 문]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---




## sorted 함수 + list 내부에서 반복문 작성 연습
sorted() 함수는 문자열의 알파벳 순으로 정렬하거나, 숫자의 경우에는 오름차순으로 정렬해준다. 즉, 1, 5, 3 라는 값이 나열되어 있으면 1, 3, 5 로 sorted 시켜준다.

리스트를 생성하는 쉬운 방법은 리스트 안에 바로 for 문과 같은 반복문을 사용해서 만들 수 있다. 아래와 같이 for 문을 사용하여 i 를 10 번 반복 하도록 한다. 보통 for 문의 경우 아래 쪽에 i 가 들어가서 수행되는 결과를 나오는데, 여기서는 for 문 앞쪽에 해당 되는 출력을 나타낸다. 그리고, []의 기호가 리스트를 의미한다. 바로 i 를 0 부터 9 까지 반복하는 값을 생성해주며, sorted 함수를 앞에 적용하면 이 값들을 오름차순으로 정리한다. 이번 예제에서는 이미 정렬 되어 있어서 살짝 의미는 없다.


```python
sorted ( [i for i in range(10)] )
```




    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]


