# 백준 12788번 - '제 2회 IUPC는 잘 개최될 수 있을까?' (실버4)

```
import sys; input = sys.stdin.readline 

n = int(input())
m, k = map(int,input().split())

a_list = list(map(int,input().split()))
a_list.sort(reverse=True)


answer = 0
count = 0
for i in range(n):
    if answer + a_list[i] >= m*k: count = i; break
    else: answer += a_list[i]

if answer == sum(a_list): print("STRESS")
else: print(count+1)
```

그리디 알고리즘 문제.  
list 정렬한 뒤 그리디 알고리즘 대로 풀면 된다.  
그리디 알고리즘에 대해 문제도 많이 풀어보고 많이 공부한 상태라면  
어렵지 않게 해결 가능.  