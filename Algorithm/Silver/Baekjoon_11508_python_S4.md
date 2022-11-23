# 백준 11508번 - '2+1 세일' (실버4)

```
import sys; input = sys.stdin.readline 

n = int(input())
n_list = [int(input()) for _ in range(n)]
n_list.sort(reverse=True)

answer_list = [n_list[i] for i in range(n) if (i+1)%3 != 0]
print(sum(answer_list))
```

그리디 알고리즘 문제.  
정렬을 활용하여 어떻게 조합하여 구매해야 최소값이 나오는지 이해한다면  
쉽게 해결할 수 있는 문제이다.  