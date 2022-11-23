# 백준 12782번 - '비트 우정지수' (실버4)

```
import sys; input = sys.stdin.readline 
from math import ceil

t = int(input())

for i in range(t):
    n_list = input().split()
    left = list(n_list[0])
    right = list(n_list[1])


    temp = []
    for i in range(len(left)):
        if left[i] == right[i]: temp.append("T")
        else: temp.append("F")

    l_cnt = left.count("1")
    r_cnt = right.count("1")
    f_cnt = temp.count("F")


    answer = 0
    if l_cnt != r_cnt: 
        answer += abs(l_cnt-r_cnt)
        f_cnt -= abs(l_cnt-r_cnt)

    answer += ceil(f_cnt/2)

    print(answer)
```

그리디 알고리즘 문제.  
약간의 수학적 고민을 좀 해봐야 한다.  

나의 경우 왼쪽 오른쪽 이진수의 1의 갯수 그리고 서로 같은 자리에 같은 숫자가 있는지에 대한 검사를  
먼저 진행하였다.  

이후 총 세개의 숫자(왼쪽에 '1' 갯수/오른쪽에 '1' 갯수/같은 자리에 같은 숫자가 있는지)들의 관계를 통해  
정답을 도출했다.  