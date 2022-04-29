# [파이썬(Python)] try 와 catch 를 활용한 예외 처리
이전 함수 input() 을 사용하여 사용자가 타이핑한 숫자를 읽어 정수로 파싱하는 프로그램 코드를 살펴보았다. 또한 이렇게 코딩하는 것이 얼마나 위험한 것인지도 살펴보았다.


```python
speed = input('What is the airspeed velocity of an unladen swallow?')
int(speed)
```

    What is the airspeed velocity of an unladen swallow?abc
    


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-3-8b25c792a028> in <module>
          1 speed = input('What is the airspeed velocity of an unladen swallow?')
    ----> 2 int(speed)
    

    ValueError: invalid literal for int() with base 10: 'abc'


결과 값을 이상하게 넣긴 했지만, 어쨌든 저렇게 정수가 아닌 값을 넣을 수도 있을 것이다. 오류가 발생하면 역추적해서 그 지점에서 즉시 멈추게 된다. 다음에 오는 문장은 실행하지 않는다. 화씨 온도르 섭씨 온도로 변환하는 간단한 프로그램이 있다.


```python
inp = input('Enter Fahrenheit Temperature: ')
fahr = float(inp)
cel = (fahr - 32.0) * 5.0 / 9.0
print (cel)
```

    Enter Fahrenheit Temperature: abc
    


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-5-ec3e26648e8d> in <module>
          1 inp = input('Enter Fahrenheit Temperature: ')
    ----> 2 fahr = float(inp)
          3 cel = (fahr - 32.0) * 5.0 / 9.0
          4 print (cel)
    

    ValueError: could not convert string to float: 'abc'


위의 코드를 실행해서 숫자가 아닌 'abc' 라는 적절하지 않은 입력값을 넣어보았다. 다소 불친절한 오류 메시지와 함께 간단히 작동을 멈춘다. 이런 종류를 예측하거나, 여측하지 못한 오류를 다루기 위해서 파이썬에는 'try / except' 로 불리는 조건 실행 구조가 내장되어 있다. try 와 except 의 기본적인 생각은 일부 명령문에 문제가 있다는 것을 사전에 알고 있고, 만약 그 때문에 오류가 발생하게 된다면 대신 프로그램에 추가해서 명령문을 실행한다는 것이다.

except 블록의 문장은 오류가 없다면 실행되지 않는다. 문장 실행에 대해서 파이썬 try, except 기능을 보험으로 생각할 수도 있다.

온도 변환기 프로그램을 다음과 같이 재작성해보자.


```python
inp = input('Enter Fahrenheit Temperature: ')
try:
    fahr = float(inp)
    cel = (fahr - 32.0) * 5.0 / 9.0
    print (cel)

except:
    print ('Please enter a number')
```

    Enter Fahrenheit Temperature: abc
    Please enter a number
    

위와 같이 try: 이후에 문제가 발생할지도 모르는 부분의 statement 를 포함시키고, except: 이후로는 문제가 발생했을 때, 뭔가 알려주는 메시지를 입력하도록 하였다. abc 를 동일하게 입력해보니, 숫자를 넣으라고 했다.

파이썬 try 블록 문장을 우선 실행하는데, 만약 모든 것이 순조롭다면, except 블록을 건너뛰고, 다음 코드를 실행한다. 만약 try 블록에서 except 이 발생하면, 파이썬은 try 블록에서 빠져나와 except 블록 문장을 수행한다.

try 문으로 예외사항을 다루는 것이 예외 처리한다 (catching an exception) 고 부른다. 예제에서 except 절에서는 단순히 오류 메시지를 출력만 한다. 대체로, 예외 처리를 통해서 오류를 고치거나, 재시작하거나, 최소한 프로그램이 정상적으로 종료될 수 있게 한다.
