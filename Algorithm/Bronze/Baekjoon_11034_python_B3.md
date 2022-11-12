# 백준 11034번 - '캥거루 세마리2' (브론즈3)

```
(1)
while True:
    try:
        n = list(map(int,input().split()))

        cnt = 0

        a = abs(n[0] - n[1]) 
        b = abs(n[1] - n[2])


        if a>b:     # c가 a, b 사이로 들어옴
            while True:
                n.sort()
                if n[0] +1 == n[1] and n[1] +1 == n[2]: print(cnt); break
                n[2] = n[1]-1
                cnt += 1
                
                
        elif a<=b:  # a가 b, c 사이로 들어옴
            while True:
                n.sort()
                if n[0] +1 == n[1] and n[1] +1 == n[2]: print(cnt); break
                n[0] = n[1]+1
                cnt += 1
    except:
        break
--------------------------------
(2)
while True:
    try:
        a, b, c = map(int,input().split())

        d = max(b-a, c-b)
        print(d-1)
    except:
        break
```

그리디 알고리즘 문제.  
자꾸 틀렸지만 차근차근 풀어나가다보니 금방 풀린 문제 였다.  
나는 (1)으로 제출해서 성공했지만  
나중에는 더 간결하고 명확한 (2) 풀이도 있다는걸 알게 되었다.  
