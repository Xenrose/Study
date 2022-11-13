# 백준 14659번 - '한조서열정리하고옴ㅋㅋ' (브론즈1)

```
n = int(input())
hanzo = list(map(int,input().split()))


cnt = 0
ret = []

temp = hanzo[0]
for i in range(1,n):
    if hanzo[i] > temp:
        temp = hanzo[i]
        ret.append(cnt)
        cnt = 0
    else:
        cnt += 1
        if i==(n-1):
            ret.append(cnt)



print(max(ret))
```

그리디 알고리즘 문제.  
별다른 설명 없이 그리디 알고리즘에 맞게 차근차근 풀면 어렵지 않게 해결할 수 있다.  
