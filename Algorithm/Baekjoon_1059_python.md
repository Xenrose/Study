# 백준 1059번 - 좋은 구간

```
l = int(input())

s = list(map(int, input().split()))

n = int(input())


check = False
if n not in s:
    s.append(n)
    check = True

s.sort()

ret = s.index(n)

frist = s[ret-1]
n = s[ret]
last = s[ret+1]


if check == True:
    if ret == 0:
        print((last - n)*(n) - 1)
    elif ret != 0:
        print((last - n)*(n - frist) - 1)
elif check == False:
    print("0")
```

제법 헤맨 문제이다.  

핵심은 집합(list) S에 n을 추가하고  
list S를 정렬한 뒤 n의 앞 뒤 원소간의 관계를 파악하면 되는 문제이다.

그리고 총 3가지 경우의 수를 볼 수 있다.
1. n값이 이미 list S에 존재하는 경우 - 문제의 조건에 따라 이 경우 좋은 구간은 "0"개 이다.
2. list S 내 n값보다 작은 원소가 존재하는 경우 - 이 경우 n이 포함된 상태로 정렬된 list S 기준   
A = n의 index -1가 되겠고 B = n의 index +1 가 되겠다.  
그렇다면 대소관계는 A < n < B가 된다.  
3. list S 내 n값보다 작은 원소가 존재하지 않는 경우

***3번의 경우***를 생각하지 못해서 오래 헤맸다.
list S 내 n값보다 작은 원소가 존재하지 않을 경우
2번의 케이스에서 A = 1이 된다.

위 세가지 경우의 수를 유념하여 코드를 짜다보면 아주 쉽게 풀리는 문제이다.