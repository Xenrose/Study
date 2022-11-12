# 백준 4796번 - '캠핑' (브론즈1)

```
# p 일 중 L일 동안만 사용 가능
# 강산이는 v일짜리 휴가를 시작
# 1 < L < p < v
# 강산이는 최대 며칠동안 사용가능?

cnt = 1
while True:
    answer = 0

    l, p, v = map(int,input().split())
    if l==p==v==0: break

    answer += (v//p)*l
    v %= p
    

    if v>=l:
        answer += l
    elif v < l:
        answer += v
    
    print("Case {0}: {1}".format(cnt, answer))
    cnt += 1
```

그리디 알고리즘 문제.  
어렵지 않고 차분히 풀면 쉽게 풀 수 있다.  