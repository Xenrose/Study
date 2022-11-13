# 백준 25400번 - '제자리' (브론즈1)

```
n = int(input())
a = list(map(int,input().split()))

cnt = 1

for i in range(n):
    if cnt == a[i]:
        cnt += 1

print(n-(cnt-1))
```

그리디 알고리즘 문제.  

핵심은 반드시 list 내 숫자를 지울 필요 없다는거다.  
조건에 안맞으면 list에서 요소를 지운다던가 굳이 그럴 필요 없이  
왼쪽부터 차례대로 list의 요소를 읽어갈때  
1을 시작으로 1씩 증가하는 요소가 각각 몇개인지만 센다면  
어렵지 않게 풀 수 있다.