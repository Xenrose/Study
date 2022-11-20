# 백준 16208번 - '귀찮음' (실버5)

```
n = int(input())
n_list = list(map(int,input().split()))
n_list.sort()

n_width = sum(n_list)

ret = 0
for i in n_list:
    ret += i*(n_width-i)
    n_width -= i

print(ret)
```

그리디 알고리즘 문제.  
정렬하는 법과 x*y의 값이 최소가 되는 조건만 알면  
이후는 그리디 알고리즘대로 풀면 어렵지 않게 풀 수 있는 문제