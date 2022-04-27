# [생물정보학 (Bioinformatics)] complement 만들기
상보적인 관계를 가지고 있는 DNA 에서 read 방향을 고려하면 ACTG 라고 된 read 가 있다면 반대로 읽으면서 상보적인 관계로 읽어야 한다. 그러면 G 의 complement 인 C 가 먼저 오고 거꾸로 읽어서 방향성을 고려한 complement 는 CAGT 가 된다. 아래는 코드를 작성한 것이다.


```python
def complement(read):
    res = ""
    for i in range(len(read)-1, -1, -1):
        if read[i] == "A":
            res += "T"
        elif read[i] == "C":
            res += "G"
        elif read[i] == "G":
            res += "C"
        elif read[i] == "T":
            res += "A"
        else:
            print ('Error in complement')
    return res

test = 'AGTCCGAGG'
result = complement(test)
print (result)

```

    CCTCGGACT
    

def 로 함수들을 정의하였고, if 와 elif 를 사용해 각 경우에 대해 작성했다. range() 함수를 사용해서 -1 즉 반대 방향의 방향성을 정했다.
