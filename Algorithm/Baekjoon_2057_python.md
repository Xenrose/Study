# 백준 2057번 - 팩토리얼 분해

```
from math import factorial


n = int(input())
if n == 0:
    print("NO")
else:
    fac_list = [factorial(i) for i in range(21) if factorial(i) <= n]
    fac_list.sort(reverse = True)


    for i in fac_list: 
        if n >= i: n -= i
        elif n < i: pass



    if n == 0: print("YES")
    elif n != 0: print("NO")
```

2시간 동안 푼 문제이다.  

핵심은 팩토리얼 수로만 구성된 list를 만든 뒤  
내림차순 정렬하여  
for문으로 큰 수부터 n을 빼주면 된다.  

최종적으로 n이 0이 된다면 YES  
그렇지 않다면 NO를 출력해주면 된다.
