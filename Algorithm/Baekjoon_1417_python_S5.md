# 백준 1417번 - 국회의원 선거 (실버5)

```
import sys

n = int(input())
candidate = [int(input()) for _ in range(n)]
if n==1: print("0"); sys.exit()


dasom = candidate[0]
another = candidate[1:]

cnt = 0
while True:
    if max(another) >= dasom:
        idx = another.index(max(another))
        another[idx] -= 1
        dasom += 1
        cnt += 1
    
    if dasom > max(another):
        print(cnt)
        break
```

쉬운 문제

그리디 알고리즘으로 차근차근 풀면 어렵지 않게 금방 풀 수 있다.