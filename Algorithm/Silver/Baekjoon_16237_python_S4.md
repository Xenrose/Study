# 백준 16237번 - '이삿짐센터' (실버4)

```
import sys; input = sys.stdin.readline 

a,b,c,d,e = map(int,input().split())

cnt = e+d
a -= d

while c>0:
    cnt += 1
    if b>0:
        c -= 1
        b -= 1
    elif a>0:
        c -= 1
        a -= 2
    else:
        c -= 1

while b>0:
    cnt += 1
    if b>1 and a>0:
        b -= 2
        a -= 1
    elif b>0 and a>0:
        b -= 1
        a -= 3
    else:
        b -= 2

while a>0:
    cnt += 1
    a -= 5

print(cnt)
```

그리디 알고리즘 문제.  
또한 구현 문제 답게 코드가 비교적 길다.  

문제의 풀이는 그냥 모든 경우의 수를 전부 확인하여 코드로 옮기는 것.  
나는 이게 제법 어려워서 구글링을 했다.  

조금 헤깔릴 수도 있으나 코드 자체는 상당히 단순한 편.  
이런 문제는 쉽게 쉽게 해결할 수 있도록 공부를 열심히 하자.  