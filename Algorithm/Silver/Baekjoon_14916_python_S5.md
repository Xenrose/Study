# 백준 14916번 - '거스름돈' (실버5)

```
n = int(input())
coin = 0

if n==1 or n==3: pass
elif n%5 == 1 or n%5 == 3:
    coin += (n//5)-1
    n %= 5
    n += 5
else:
    coin += (n//5)
    n %= 5


coin += n//2
n %= 2

if n==0: print(coin)
elif n!=0: print("-1")
```

그리디 알고리즘 문제.  
일반적인 거스름돈 문제와 달리 특수한 상황이 있다.  
이를테면 5로 전부다 나눈 나머지가 2로 나눠지지 않으나  
5를 일부만 나눈 후 2로 나눌 경우 완전히 나눠지는 경우이다.  

이 경우만 잘 생각하며 문제를 푼다면 그렇게 어렵지 않게 풀 수 있다.  