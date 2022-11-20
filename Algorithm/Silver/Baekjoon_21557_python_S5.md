# 백준 21557번 - '불꽃놀이' (실버5)

```
n = int(input())
n_list = list(map(int,input().split()))


left = n_list[0]
right = n_list[-1]
n -= 3
left -= 1
right -= 1

for _ in range(n):
    if left > right: left -= 1
    else: right -= 1

print(max(left,right))
```

그리디 알고리즘 문제.  
어렵게 생각하면 상당히 어려운 문제다.  
하지만 문제의 핵심은
1. 가장 마지막 시행은 좌측 우측 전부 1을 뺀다.
2. 좌측 혹은 우측 둘 중 높은 쪽을 1씩 뺀다.
3. 시행은 n-2회만 한다.

세가지만 기억한채 그리디 알고리즘으로 풀면 쉽게 풀린다.