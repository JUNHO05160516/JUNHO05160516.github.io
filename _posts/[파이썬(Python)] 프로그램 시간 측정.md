# [파이썬(Python)] 프로그램 시간 측정
파이썬에서 프로그램을 실행했을 때, 해당 프로그램이 돌아간 시간을 측정하는 방법에 대해 알아보자. start 변수에 timeit.default_timer() 세팅하고, end에도 마찬가지로 작성한다. 그 사이에 내가 실행하고자 하는 코드를 작성한다.


```python
import timeit

start = timeit.default_timer()

for i in range(100000000):
    i

end = timeit.default_timer()
(end - start)
```




    3.6758402000000103



예로, for 문의 i를 메모리로 저장하는 형태를 진행했다. 약 3.6 초 걸린 것을 확인할 수 있다. 기본 세팅이 '초' 단위기 때문에 '분'이나, '시' 단위로 표현하고 싶을 때에는 임의로 60을 나누어 분을 나타내거나, 3600을 나누어 시간으로 나타내면 된다. 위와 같이 end - start를 하면 총 걸린 시간이 나온다.
