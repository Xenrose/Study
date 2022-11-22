# 백준 3213번 - '피자' (실버4)

```
import sys; input = sys.stdin.readline
import math


n = int(input())
n_list = [input().strip() for _ in range(n)]


cnt = 0
rest = 0

a = n_list.count("1/2") # 1/2 조각 갯수
b = n_list.count("3/4") # 3/4 조각 갯수
c = n_list.count("1/4") # 1/4 조각 갯수

# 1/2 + 1/2 = 피자 1개
if a>=2: cnt += a//2; a %= 2; rest += a*2
elif a<2: rest += a*2

# 1/4 + 3/4 = 피자 1개
if b>=c: cnt +=b; c = 0
elif b<c: cnt +=b; c -=b; rest += c


cnt += math.ceil(rest/4)

print(cnt)
```

그리디 알고리즘 문제.  
어렵지는 않으나 상당이 헤깔리게 만들어 놓은 문제.  

친구에게 피자를 줄때  
전체 피자 중 1/2 크기의 1조각  
전체 피자 중 3/4 크기의 1조각  
전체 피자 중 1/4 크기의 1조각을 준다고 생각하면 조금 더 직관적이다.  


그리고 위 기본 전제를 기반으로  
1/2 + 1/2 = 피자 1판  
1/4 + 3/4 = 피자 1판이므로 


1/2의 피자 갯수가 2개가 넘는다면 a//2개 만큼 피자 수를 증가시키고 나머지는 rest에 a\*2개 만큼 넣는다.  
만일 1/2 피자 갯수가 2개가 넘지 못한다면 바로 rest에 a\*2개 만큼 넣는다.  

이후 1/4 + 3/4 케이스를 전부 다 세어준 뒤  
남은 1/4 조각의 갯수만큼 rest에 넣어준다.


최종적으로 rest의 갯수 중 소수점 첫번째 자리에서 무조건 올림 해주면 된다.  
(ex. rest=4일 경우 cnt +=1 / rest=5일 경우 cnt +=2)