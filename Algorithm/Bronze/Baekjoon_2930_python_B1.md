# 백준 2930번 - '가위 바위 보' (브론즈1)

```
from collections import deque 


def rsp(temp1, temp2):
    rsp = deque(["R", "S", "P"])

    while rsp[1] != temp1:
        rsp.append(rsp.popleft())
        
    return rsp.index(temp2)



r = int(input())
player1 = list(input())

n = int(input())
players = []
for i in range(n):
    t = list(input())
    players.append(t)


point_1 = 0
for j in range(n):
    for i in range(r):
        point_1 += rsp(player1[i],players[j][i])
print(point_1)


point_2 = 0
for j in range(len(players[0])):
    R_temp = 0
    S_temp = 0
    P_temp = 0
    for i in range(len(players)):
        R_temp += rsp("R",players[i][j])
        S_temp += rsp("S",players[i][j])
        P_temp += rsp("P",players[i][j])
        
    point_2 += max(R_temp, S_temp, P_temp)

print(point_2)
```

그리디/브루트포스 알고리즘 문제.  
내가 잘 모르기 때문인걸까  
왜 이게 브론즈1 문제인지 모르겠다.  

푸는데 정말 힘들었다.  

첫번째 출력은 어렵지 않게 함수를 만들어서 해결했지만  
두번째 출력은 아무리 해도 갈피를 잡지 못했으나 구글링을 통해 브루트포스로 풀면 된다는 힌트를 얻었다.  

다 풀고나서 보니깐 쉬워 보이지만 푸는 동안에는 제법 어려웠던 문제.  

핵심은 
1. 함수를 만들고 '큐'를 이용하여 점수를 반환해주는것
    * 해당 방법을 활용하면 조건문을 길게 늘여뜨릴 필요 없음
2. 두번째 출력, 상근이가 가장 최고 점수를 받는 방법은 브루트 포스로 그냥 R,S,P 하나씩 냈을때 모든 경우의 수에서  
몇점을 받는지 전부 세어보는것.  
어자피 가위 바위 보 게임이라서 경우의 수가 그리 많지 않기에 가능했다.  