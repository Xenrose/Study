# 백준 2847번 - '게임을 만든 동준이' (실버4)

```
import sys; input = sys.stdin.readline

n = int(input())
n_list = [int(input()) for _ in range(n)]

cnt = 0


for i in range(n-1,0,-1):
    if n_list[i] <= n_list[i-1]:
        temp = n_list[i-1]
        n_list[i-1] = n_list[i] -1
        cnt += (temp - n_list[i-1])

print(cnt)
```

그리디 알고리즘 문제.  
쉬운 문제이다.   
팁은 list를 역순으로부터 카운팅 하는것이다.  
