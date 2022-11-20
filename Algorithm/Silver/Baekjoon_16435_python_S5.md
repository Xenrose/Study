# 백준 16435번 - '스네이크버드' (실버5)

```
n, l = map(int,input().split())
h_list = list(map(int,input().split()))
h_list.sort()

for i in h_list:
    if l >= i: l += 1
    elif i > l: break

print(l)
```

그리디 알고리즘 문제.  
list를 정렬할 줄 안다면 쉬운 문제이다.  
