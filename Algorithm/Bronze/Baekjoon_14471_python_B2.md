# 백준 14471번 - 포인트 카드 (브론즈2)

```
n, m = map(int,input().split())

ret = []

for i in range(m):
    a, b = map(int,input().split())
    if n>a:
        ret.append(n-a)

ret.remove(max(ret))

print(sum(ret))
```

그리디 알고리즘 문제  
쉽다.