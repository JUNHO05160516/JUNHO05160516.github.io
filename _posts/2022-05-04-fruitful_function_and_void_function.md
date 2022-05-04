---
layout: single
title:  "[파이썬(Python)] 결과있는 함수 (fruitful function)과 빈 함수(void function)"
categories: Python
tag: [Python, 파이썬, fruitful function, void function]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---


## 결과있는 함수 (fruitful function)과 빈 함수(void function)
수학 함수와 같은 몇몇 함수는 결과를 만들어 낸다. 좀 더 좋은 이름이 없어서, 결과를 만들어 내는 함수를 결과있는 함수 (fruitful functions) 라고 명명한다. 아래와 같은 print_twice() 함수는 print 라는 액션을 수행하지만, 결과를 만들지는 않는 함수를 빈 함수 (void functions) 라고 부른다.


```python
def print_twice(bruce):
    print(bruce)
    print(bruce)
```

결과있는 함수를 호출할 때에는 결과값을 가지고 뭔가를 하려고 한다. 예를 들어, 결과값을 변수에 대입하거나, 표현식의 일부로 사용할 수 있다.


```python
import math
x = math.cos(math.pi)
x
```




    -1.0



위의 경우, cose 계산 결과를 x 에 저장했다. 아래의 경우, math.sqrt() 함수를 사용하여 구한 함수 반환값을 사용하여 계산한 값을 golden 변수에 저장하여 출력해보았다.


```python
golden = (math.sqrt(5) + 1 ) / 2
golden
```




    1.618033988749895



인터랙티브 모드에서 함수를 호출할 때, 파이썬은 결과를 화면에 출력한다.


```python
math.sqrt(5)
```




    2.23606797749979



빈 함수 (void function) 는 화면에 출력하거나 무엇인가 다른 효과를 가지지만, 반환값이 없다. 빈 함수를 사용하여 결과에 변수를 대입하면, None 으로 불리는 특별한 값을 얻게 된다.


```python
result = print_twice('Bing')
```

    Bing
    Bing
    


```python
print(result)
```

    None
    

맨 처음 만든 print_twice() 함수를 사용해보자. result 라는 변수에 해당 값을 저장했지만, 막상 변수의 값을 print 해보면 None 이라는 값을 출력 된다. None 값은 자신만의 특별한 값을 가지며, 문자열 'None' 과 같지 않다.


```python
print(type(None))
```

    <class 'NoneType'>
    

함수에서 결과를 반환하기 위해서, 함수 내부에 return 문을 사용한다. 예를 들어, 두 숫자를 더해서 결과를 반환하는 addtwo 라는 간단한 함수를 작성할 수 있다.


```python
def addtwo (a, b):
    added = a + b
    return added
```

위와 같이 a 와 b 를 인자로 바아서 둘을 더한 값을 return 하는 함수를 만들었고, 아래에서 함수를 실행시켜서 그 결과값을 x 에 저장하여 출력해보았다. 정확히 3 + 5 = 8 값이 나온다.


```python
x = addtwo(3,5)
print (x)
```

    8
    
