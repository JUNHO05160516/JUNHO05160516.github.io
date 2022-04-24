# [파이썬(Python)] _pickle() 함수
피클은 데이터를 문자열이 아닌 객체의 형태 그대로 기억하면서 저장할 수 있게 해줌. 
즉, 데이터가 딕셔너리로 저장되어 있으면 그 상태를 그대로 보존하여 저장함.
my_Dict 변수에 딕셔너리를 정의한다. 하나의 key와 value로 'hi' 문자열과 'junho' 문자열을 입력한다.


```python
my_Dict = {}
my_Dict['hi'] = 'junho'
```

이 데이터를 피클의 형태로 저장하고자 하면 open 함수를 사용해 보자. 압축된 형태로 저장하기 위해서 gzip.open 함수를 사용하고, byte로 저장하고자 'wb' 옵션을 넣어준다. 그리고, gzip.open() 함수에서 'test.pkl.gz' 형태의 인자를 처음 넣었다. 'test'는 파일 이름이 된고, pkl.gz 형태를 넣어주었다. f_out 변수에 넣어주자. 


```python
import gzip

f_out = gzip.open('test.pkl.gz','wb')
```

cpickle.dump() 함수를 사용해서 my_Dict 변수를 f_out 파일에 넣어준다. 


```python
import _pickle as cpickle

cpickle.dump(my_Dict, f_out)
```

자료 생성은 완료했다. 다시 불러들이고 싶으면, gzip.open() 함수에서 파일 이름을 넣어보자. f_in 이라는 변수에 파일을 다시 가져오고, cpickle.load() 함수로 다시 불러와서 New 라는 변수에 파이썬에서 사용할 수 있는 형태의 변수로 기억시키자.  


```python
f_in = gzip.open('test.pkl.gz')
New = cpickle.load(f_in)
New
```




    {'hi': 'junho'}


