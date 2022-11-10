# 백준 11256번 - '사탕' (실버5)

```
t = int(input())


for k in range(t):
    j, n = map(int,input().split())
    box_size = []
    
    for i in range(n):
        a, b = map(int,input().split())
        box_size.append(a*b)

    box_size.sort(reverse=True)

    idx = 0
    while j>0:
        j -= box_size[idx]
        idx += 1

    print(idx)
```

그리디 알고리즘  
쉽게 해결할 수 있다.  
