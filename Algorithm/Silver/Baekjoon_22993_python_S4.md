# 백준 22993번 - '서든어택 3' (실버4)

```
import sys; input = sys.stdin.readline 

n = int(input())

if n==1: print("Yes")
else:
    n_list = list(map(int,input().split()))

    junwon = n_list[0]
    n_list = n_list[1:]
    n_list.sort()
    last_idx = len(n_list)


    for i in range(last_idx):
        if i+1 == last_idx:
            if junwon > n_list[i]: print("Yes")
            elif junwon <= n_list[i]: print("No")
        elif i+1 != last_idx:
            if junwon > n_list[i]: junwon += n_list[i]
            elif junwon <= n_list[i]: print("No"); break
```

그리디 알고리즘 문제.  
쉬운 문제이나. 계속해서 100% 에서 틀렸다고 나왔다.  
찾아보니 n이 1인 케이스를 고려를 안해서 생긴 일.  

아직 나는 멀었다. 열심히 공부해야 한다.  