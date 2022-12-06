# 백준 20363번 - '당근 키우기' (실버4)

```
import sys; input = sys.stdin.readline 

x, y = map(int,input().split())

cnt = 0

t_min = min(x,y)
t_max = max(x,y)

cnt += t_max
cnt += t_min
cnt += t_min//10

print(cnt)
```

그리디 알고리즘 문제.  
햇빛과 물을 주는 횟수가 어느 공식으로 최솟값이 나타나는지만 안다면  
아주 쉽게 풀 수 있는 문제.  

