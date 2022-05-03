---
layout: single
title:  "[파이썬(Python)] 수학 함수 (import math)"
categories: Python
tag: [Python, 파이썬, import math, math]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---


## 수학 함수
파이썬은 가장 친숙한 수학 함수를 제공하는 수학 모듈이 있다. 수학 모듈을 사용하기 전에, 수학 모듈 가져오기를 실행한다.


```python
import math
```

위 명령문은 math 라는 모듈 객체를 생성한다. 모듈 객체를 출력하면, 모듈 객체에 대한 정보를 얻을 수 있다.


```python
print (math)
```

    <module 'math' (built-in)>
    

모듈 객체는 모듈에 정의된 함수와 변수를 담고 있다. 함수 중에서 한 함수에 접근하기 위해서는, 모듈 이름과 함수 이름을 명시해야 하는데, 둘은 점 (구두점)으로 구분된다. 이런 형식을 점 표기법 (dot notation) 이라고 부른다.


```python
signal_power = 3
noise_power = 3
ratio = signal_power / noise_power
decibel = 10 * math.log10(ratio)
print(decibel)
```

    0.0
    

위의 경우, 4 번째 줄에 log10() 이라는 함수를 사용하기 위해서 모듈인 math 이름을 쓰고, 그 뒤에 구두점을 찍고, log10() 함수를 썻다. 그러면 해당 모듈에 포함된 함수를 사용할 수 있다.


```python
radians = 0.7
height = math.sin(radians)
print(height)
```

    0.644217687237691
    

위의 경우에는 sin() 함수를 사용하였고, 모듈 math 로 부터 가져왔다.


```python
degrees = 45
radians = degrees / 360 * 2 * math.pi
print(radians)
```

    0.7853981633974483
    

위의 경우, pi 라는 파이 값을 가져오는데, 함수가 아닌 pi 라는 변수를 가져오는데도 사용할 수 있다. 모듈 math 로 부터 pi 라는 변수를 math.pi 로 가져올 수 있다.


```python
math.sqrt(4)
```




    2.0



루트는 math 모듈에서 sqrt() 함수를 사용해서 가능하고, 위에서 4 에 루트를 쓰우니 2 의 값을 출력하는 것을 확인할 수 있다.
