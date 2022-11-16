# 백준 17224번 - 'APC는 왜 서브태스크 대회가 되었을까?' (브론즈1)

```
n, l, k = map(int,input().split())

n_list = [list(map(int,input().split())) for _ in range(n)]


easy_q = 0
hard_q = 0
for i in n_list:
    if l >= i[1]: hard_q += 1; easy_q += 1
    elif l >= i[0]: easy_q += 1


if hard_q > k: hard_q = k
if easy_q > k: easy_q = k


print((hard_q*40)+(easy_q*100))
```

그리디 알고리즘 문제.  
어렵지 않게 풀 수 있다.

백준 알고리즘 분류로 '정렬'이 들어가 있지만  
굳이 정렬하지 않아도 해결하는데 어려움은 없다.
