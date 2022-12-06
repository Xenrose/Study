# 백준 25632번 - '소수 부르기 게임' (실버4)

```
import sys; input = sys.stdin.readline 
from math import sqrt

def is_prime(num):
    for i in range(2,int(sqrt(num))+1):
        if num%i == 0: return False
    return True


a, b = map(int,input().split())
yt_list = [i for i in range(a,b+1) if is_prime(i)]
a, b = map(int,input().split())
yj_list = [i for i in range(a,b+1) if is_prime(i)]


temp = []
for i in yt_list:
    if i in yj_list: 
        temp.append(i)

if len(temp)%2 != 0: yt_list.append(1)


if len(yt_list)==len(yj_list): print("yj")
elif len(yt_list) < len(yj_list): print("yj")
elif len(yt_list) > len(yj_list): print("yt")
```

그리디 알고리즘 문제.  
지금까지 알고리즘 문제를 풀어본 결과  
직관적으로 해결법이 떠오르지 않는다면 왠만해선 수학적 센스를 필요로 하는것 같다.  

이 문제 또한 그렇다.  
  
단순한 해결법으로는 용태와 유진 각각 자신의 list를 만들고  
각각 a와 b를 입력 받고 그 사이에 있는 모든 소수를 자신의 list에 넣었을때  
그 list의 크기가 큰 쪽이 이긴다.  


단, 특수한 사례가 있는데 그것은 중복된 소수이다.  
중복된 소수의 갯수가 짝수라면 결국 한명씩 하나의 중복된 소수를 말하기 때문에  
이 경우 승부의 영향은 없다.(결국 list의 크기가 큰쪽이 이김)  

중복된 소수의 갯수가 홀수라면 마지막에 용태가 한번 더 (중복된 소수를)부를 수 있으므로 용태가 유리하다.  
그러므로 용태의 list에 1을 추가해준 상태로 서로의 list의 크기를 비교하면 정답이 나온다.  
