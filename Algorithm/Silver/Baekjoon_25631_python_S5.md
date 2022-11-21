# 백준 25631번 - '마트료시카 합치기' (실버5)

```
from collections import deque

n = int(input())
n_list = list(map(int,input().split()))
n_list.sort()
n_list = deque(n_list)

cnt = 0
while n_list:
    temp = 0
    for i in range(len(n_list)):
        if n_list[0] > temp: temp = n_list.popleft()
        else: n_list.append(n_list.popleft())
    cnt += 1

print(cnt)
```

그리디 알고리즘 문제.  
정렬과 큐를 활용하면 비교적 쉽게 해결할 수 있다.  
핵심은 
오름차순 정렬된 큐의 첫번째 원소를 기준으로 그 다음 원소가   
첫번째 원소보다 크다면 append 하지 않고 그대로 삭제한다.  
만약 이전 원소보다 다음 원소가 더 작다면 append를 해준다.  
이런 식으로 반복문으로 정렬된 큐 전체를 검사해준 뒤 cnt를 1 증가시켜주는 과정을  
큐 안에 요소가 사라질때까지 반복해준다.  


