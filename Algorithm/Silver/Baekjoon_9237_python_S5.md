# 백준 9237번 - '이장님 초대' (실버5)

```
def check_num(i, n):
    if n > i: return 0
    else: return i-n

n = int(input())
t_list = list(map(int,input().split()))
t_list.sort(reverse=True)

day = 1

t_list = [check_num(t_list[i],n-i) for i in range(n)]


day += n
day += max(t_list)


print(day+1)
```

그리디 알고리즘 문제.  
핵심은
1. 오름차순으로 정렬할 것
2. list에 요소를 하나씩 추가할 수록 기존의 요소는 1씩 더 줄어들 것
3. 나무가 다 자란뒤 이장님을 초대한다는 것