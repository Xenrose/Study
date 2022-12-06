# 백준 25943번 - '양팔저울' (실버4)

```
import sys; input = sys.stdin.readline 

n = int(input())
n_list = list(map(int,input().split()))


left = [n_list[0]]
right = [n_list[1]]


for i in range(2,n):
    if sum(left) == sum(right): left.append(n_list[i])
    elif sum(left) > sum(right): right.append(n_list[i])
    elif sum(left) < sum(right): left.append(n_list[i])

answer = abs(sum(left)-sum(right))
weights = [100,50,20,10,5,2,1]


cnt = 0
for weight in weights:
    cnt += answer//weight
    answer %= weight

print(cnt)
```

그리디 알고리즘 문제.  
가장 기본적인 문제인 거스름돈 걸러주기 문제의 변형 버전으로  
이 문제 역시 어렵지 않게 해결 가능하다.  
