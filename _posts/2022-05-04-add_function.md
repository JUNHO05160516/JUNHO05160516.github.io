## [파이썬(Python)] 신규 함수 추가
파이썬 설치 시 함께 있는 함수만 사용하진 않을 것이다. 새로운 함수를 추가하는 것도 가능하다. 함수 정의 (function definition) 는 신규 함수명과 함수가 호출될 때 실행될 열련의 문장을 명세한다. 신규로 함수를 정의하면, 프로그램 실행 중에 반복해서 함수를 재사용할 수 있다. 다음의 예제가 있다.


```python
def print_lyrics():
    print ('I am a okay')
    print ('I sleep and work')
```

def 는 '이것이 함수 정의다' 를 표시하는 예약어이다. 함수 이름은 print_lytics이다. 함수 이름을 명명 규칙은 변수명과 동일하다. 문자, 숫자, 그리고 몇몇 문장부호는 사용할 수 있지만, 첫 문자는 숫자가 될 수 없다. 함수 이름으로 예약어를 사용할 수 없고, 함수 이름과 동일한 변수명은 피해야 한다.

함수명 뒤 빈 괄호는 이 함수가 어떠한 인자도 갖지 않는다는 것을 나타낸다. 나중에 입력값으로 인자를 가지는 함수를 작성해보겠다.

함수 정의 첫 번째 줄을 머리 부문 (헤더, header) 나머지 부문을 몸통 부문 (바디, body) 라고 부른다. 머리 부문은 콜론 (:) 으로 끝나고, 몸통 부문은 들여쓰기해야 한다. 파이썬 관례로 들여쓰기는 항상 4칸 공백이다. 몸통 부문에는 제약 없이 문장을 작성할 수 있다.

print 문의 문자열은 이중 인용부호로 감싼다. 단일 인용부호나, 이중 인용부호나 차이는 없다. 대부분의 경우 단일 인용부호를 사용하고, 단일 이뇽ㅇ부호가 문자열에 나타나는 경우, 이중 인용부호를 사용하여 단일 인용부호가 출력되게 감싼다.

함수를 정의하게 되면 동일한 이름의 변수도 생성된다. 즉, 위의 예제의 경우, print_lytics() 라는 함수를 정의했을 뿐인데, 이미 이것은 변수로도 생성이 된 것이다. 그래서 print() 함수로 해당 변수를 출력하라고도 할 수 있으며, type() 함수로 해당 변수의 타입을 확인하여 출력할 수도 있다.


```python
print (print_lyrics)
```

    <function print_lytics at 0x000002E85B7B3B80>
    


```python
print (type(print_lyrics))
```

    <class 'function'>
    

print_lytics 값은 'function' 형을 가지는 함수 객체 (function object) 이다.

신규 함수를 호출하는 구문은 내장 함수의 경우와 동일하다.


```python
print_lyrics()
```

    I am a okay
    I sleep and work
    

단, 위의 함수의 겅우, 인자가 없으니, 괄호안에 아무 것도 넣지 않고 함수를 호출해야 한다. 함수를 정의 하면, 또 다른 함수 내부에서 사용이 가능하다. 예를 들어, 이전 후렴구를 반복하기 위해 repear_lytics() 함수를 작성할 수 있다.


```python
def repeat_lytics():
    print_lyrics()
    print_lyrics()
```

이렇게 하고, repeat_lyrics() 함수를 호출해보자.


```python
repeat_lytics()
```

    I am a okay
    I sleep and work
    I am a okay
    I sleep and work
    

이렇게 기존의 함수가 불러들여져서 두 번 반복하는 것을 볼 수 있다.
