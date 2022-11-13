# 백준 25496번 - '장신구 명장 임스' (브론즈1)

```
p, n = map(int,input().split())
a = list(map(int,input().split()))
a.sort()

cnt = 0
for i in a:
    if p < 200:
        cnt += 1
        p += i
    else:
        break

print(cnt)
```

그리디 알고리즘 문제.  
그리 어렵지 않게 풀 수 있다.  
