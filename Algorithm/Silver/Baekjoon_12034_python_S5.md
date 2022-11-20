# 백준 12034번 - '김인천씨의 식료품가게 (Large)' (실버5)

```
from collections import deque


t = int(input())

for k in range(t):
    n_price = int(input())
    n_list = list(map(int,input().split()))
    n_list = deque(n_list)
    ret_list = []

    f = lambda x: x*100//75    
    while n_list:
        temp_n = n_list.popleft()
        if f(temp_n) in n_list: ret_list.append(temp_n); del n_list[n_list.index(f(temp_n))]


    ret_list.sort()
    print("Case #{}: ".format(k+1),end='')
    for i in ret_list: print(i,end=' ')
    print()
```

그리디 알고리즘 문제.  
생각보다 헤맨 문제였다.  

꼭 명심해야할 부분은 주어진 가격표는 정상가-할인가 두가지가 짝지어 있다는 점.  
이를테면 예제 Case #2 에서  
12는 9의 정상가도 될 수 있고 16의 할인가도 될 수 있다.  
그렇다면 12가 3개인 이유는 3개 중 2개는 9의 정상가일테고  3개 중 1개는 16의 할인가일것이다.  
그러므로 12 세개 중 1개만이 정답이 될 수 있는것이다.  

이 부분만 명심하면 문제 해결이 가능하다.