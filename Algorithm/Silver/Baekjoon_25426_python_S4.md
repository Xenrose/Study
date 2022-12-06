# 백준 25426번 - '일차함수들' (실버4)

```
import sys; input = sys.stdin.readline 

t = int(input())
t_list = [i for i in range(1,t+1)]
t_list.sort(reverse=True)

fx_list = [list(map(int,input().split())) for i in range(t)]
fx_list.sort(reverse=True)


answer = []
for i in range(t):
    t = fx_list[i][0]*t_list[i]+fx_list[i][1]
    answer.append(t)

print(sum(answer))
```

그리디 알고리즘 문제.  
정렬하는법과 어느 순간에 값이 최대가 나오는지 이해한다면  
그 이후 부터는 아주 쉬운 문제이다.  
