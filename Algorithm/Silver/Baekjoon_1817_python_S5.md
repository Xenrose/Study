# 백준 1817번 - '짐 챙기는 숌' (실버5)

```
n, m = map(int,input().split())

if n==0: 
    cnt = 0
elif n!=0: 
    cnt = 1
    temp = 0
    for i in list(map(int,input().split())):
        if temp + i <= m:
            temp += i
        elif temp + i > m:
            cnt += 1
            temp = i

print(cnt)
```

그리디 알고리즘 문제.  
정석적인 문제로 차근차근 생각하면  
쉽게 풀 수 있다.  