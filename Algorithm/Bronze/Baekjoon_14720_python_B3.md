# 백준 14720번 - 우유 축제 (브론즈3)

```
from collections import deque

milk = [0,1,2]

milk = deque(milk)


n = int(input())
store = list(map(int, input().split()))
cnt = 0

for i in store:
    if milk[0] == i:
        cnt += 1
        milk.append(milk.popleft())

print(cnt)
```

그리디 알고리즘 문제  
큐를 사용하여 해결하면 아주 쉽게 풀 수 있다. 
