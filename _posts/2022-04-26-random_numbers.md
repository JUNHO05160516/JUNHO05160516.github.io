---
layout: single
title:  "[파이썬(Python)] 난수 (Random Numbers) 생성"
categories: Python
tag: [Python, 파이썬, random.random, random, random number]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---







### 난수 (Random Numbers) 생성
동일한 입력을 받을 때, 대부분의 컴퓨터는 매번 동일한 출력값을 생성하는 것을 결정적 (deterministric) 이라고 한다. 하지만 어떤 응용 프로그램에 대해서 컴퓨터가 예측 불가능하길 바라는 경우도 있다. 예를 들어 게임이다.

비결정론적인 것처럼 보이게 하는 방법이 있다. 의사 난수 (pseudo-random numbers)를 생성하는 알고리즘을 사용하는 방법이다. 의사 난수는 이미 결정된 연산에 의해서 생성된다는 점에서 진정한 의미의 난수는 아니지만, 이렇게 생성된 숫자만 봐서는 진정한 난수와 구별하는 것은 불가능에 가깝다.

random 모듈안에 의사 난수를 생성하는 함수가 있다. (이하 의사 난수 대신 '랜덤'으로 하겠다)

random 함수는 0.0 과 1.0 사이 ㅂ동 소수점 난수로 반환한다. random 함수는 0.0 은 포함하지만 1.0 은 포함하지 않는다. 매번 random 함수를 호출할 때 마다, 이미 생성된 아주 긴 난수열에서 하나씩 하나씩 뽑아 쓴다.


```python
import random

for i in range(10):
    x = random.random()
    print(x)
```

    0.2909927672370324
    0.12919783361626014
    0.005593281264409278
    0.940390136211522
    0.3009330049280362
    0.22241299528893643
    0.4307918086103105
    0.17901280866935765
    0.9793549176063069
    0.16920856686860175
    

random 함수는 난수를 다루는 많은 함수 중의 하나이다. randint 함수는 최저(low)와 최고(high) 매개변수를 입력받아 최저값과 최고값 사이( 최저값과 최고값을 모두 포함) 정수를 반환한다.


```python
random.randint(5,10)
```




    6



무작위로 특정 열에서 하나의 요소를 뽑아 내기 위해서는 choice를 사용한다.


```python
t = [1,2,3]
random.choice(t)
```




    3



또한 random 모듈은 정규분포, 지수분포, 감마분포 및 기타 연속형 분포에서 난수를 생성하는 함수도 제공한다.
