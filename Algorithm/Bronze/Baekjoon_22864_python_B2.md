# 백준 22864번 - '피로도' (브론즈2)

```
a, b, c, m = list(map(int,input().split()))

# a = 1시간 일해서 쌓이는 피로도
# b = 1시간 일해서 처리한 일의 양
# c = 1시간 쉴 경우 줄어드는 피로도
# m = 피로도 상한치

tired = 0
labor = 0


if a>m: print("0")
else:
    for i in range(24):
        if tired + a > m:
            tired -= c
            if tired < 0:
                tired = 0
        elif m >= tired + a:
            tired += a
            labor += b

    print(labor)
```

그리디 알고리즘 문제.
딱히 설명할 부분은 없지만 제법 헤맨 문제이다.  
피로도가 0 밑으로 내려가지 않는다는 점만 주의해주면 금방 풀리는 문제이다.  
