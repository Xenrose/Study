# 백준 25972번 - '도미노 무너트리기' (실버4)

```
import sys; input = sys.stdin.readline 

n = int(input())
n_list = [list(map(int,input().split())) for _ in range(n)]
n_list.sort()



cnt = 0
for i in range(1,n):
    if n_list[i][0] <= sum(n_list[i-1]): cnt += 1


print(n-cnt)
```

그리디 알고리즘 문제.  
과연 입력이 주어진 좌표가 오름차순으로 주어질지  
무작위로 주어질지에 대해 고민해보면 쉽게 풀릴 수 있는 문제이다.  

그 외 부분은 그저 문제를 읽고 그대로 코드로 구현하면 쉽게 풀 수 있다.  
