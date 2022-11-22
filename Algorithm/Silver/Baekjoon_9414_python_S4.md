# 백준 9414번 - '프로그래밍 대회 전용 부지' (실버4)

```
import sys; input = sys.stdin.readline 

max_money = 5*10**6

t = int(input())

for _ in range(t):
    t = -1
    temp = []
    while t!=0:
        t = int(input())
        temp.append(t)

    temp.sort(reverse=True)

    answer = 0
    for i in range(len(temp)):
        answer += (2*temp[i]**(i+1))

    if answer > max_money: print("Too expensive")
    else: print(answer)
```

그리디 알고리즘 문제.  
정렬과 함께 어느 조건에서 땅값이 최소값이 되는지 안다면 그렇게 어렵지 않게 풀 수 있다.