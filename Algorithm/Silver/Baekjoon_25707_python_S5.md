# 백준 25707번 - '팔찌 만들기' (실버5)

```
n = int(input())
n_list = list(map(int,input().split()))
n_list.sort()

ret = n_list[-1] - n_list[0]

for i in range(1,n):
    ret += (n_list[i]-n_list[i-1])

print(ret)
```

그리디 알고리즘 문제.  
정렬과 어떤 상황에서 줄의 길이가 최소값이 되는지 알고 있다면  
쉽게 해결할 수 있는 문제이다.  
