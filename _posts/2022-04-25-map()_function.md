# [파이썬(Python)] map 함수

## 1. map 함수 설명과 사용법

### 1-1) 파이썬 맵 함수 기본 설명

map(function, iterable)

첫 번째 매개변수로는 함수가 오고, 두 번째 매개변수로는 반복 가능한 자료형(리스트, 튜블 등)이 온다.
map () 함수의 반환 값은 map 객체 이기 때문에 해당 자료형을 list 혹은 tuple 형으로 변환시켜야 한다.
두 번째 인자로 들어온 반복 가능한 자료형 (리스트나 튜플)을 첫 번째 인자로 들어온 함수에 하나씩 집어넣어서 함수를 수행하는 함수이다.

따라서, map (적용시킬 함수, 적용할 값들) 식이다.
예를 들어 첫 번째 인자 값에 +1 을 더해주는 함수라고 하고 두 번째 인자에 [1,2,3,4,5] 라는 리스트를 집어 넣으면 함수 모양은 아래와 같고 map (값에 +1 을 더해주는 함수, [1,2,3,4,5]) 함수의 반환을 list()로 감싸주면 [2,3,4,5,6] 이 되는 함수이다.

### 1-2) map 함수를 사용하는 것과 아닌 것의 차이



```python
# 리스트에 값을 하나씩 더해서 새롱운 리스트를 만드는 작업
myList = [1,2,3,4,5]

# for 반복문 이용
result1 = []
for val in myList:
    result1.append(val + 1)

print (f'result1 : {result1}')
```

    result1 : [2, 3, 4, 5, 6]
    


```python
# map 함수 이용
def add_one(n):
    return n + 1

result2 = list(map(add_one, myList))
print(f'result2 : {result2}')
```

    result2 : [2, 3, 4, 5, 6]
    

## 2. map 함수 예제

### 2-1) 리스트와 map 함수


```python
import math # math.ceil 함수 사용

# 예제 1) 리스트의 값을 정수 타입으로 변환
result1 = list(map(int, [1.1, 2.2, 3.3, 4.4, 5.5]))
print(f'map(int, 리스트): {result1}')
```

    map(int, 리스트): [1, 2, 3, 4, 5]
    


```python
# 예제 2) 리스트 값 제곱
def func_pow(x):
    return pow(x,5)
    
result2 = list(map(func_pow, [1,2,3,4,5]))
print(f'map(func_pow, 리스트) : {result2}')
```

    map(func_pow, 리스트) : [1, 32, 243, 1024, 3125]
    


```python
# 예제 3) 리스트 값 소수점 올림
result3 = list(map(math.ceil, [1.1, 2.2, 3.3, 4.4, 5.5, 6.6]))
print(f'map(func_ceil, 리스트) : {result3}')
```

    map(func_ceil, 리스트) : [2, 3, 4, 5, 6, 7]
    

### 2-2) 람다와 map 함수


```python
# map 과 lambda

# 일반 험수 이용
def func_mul(x):
    return x * 2

result1 = list(map(func_mul, [5,4,3,2,1]))
print(f'map(일반함수, 리스트) : {result1}')
```

    map(일반함수, 리스트) : [10, 8, 6, 4, 2]
    


```python
# 람다 함수 이용
result2 = list(map (lambda x: x *2, [5,4,3,2,1]))
print(f'map(람다함수, 리스트) : {result2}')
```

    map(람다함수, 리스트) : [10, 8, 6, 4, 2]
    
