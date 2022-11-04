# 백준 1004번 - 어린왕자

```
import math 

def check_circle(circle, point):
    x_c = circle[0]
    y_c = circle[1]
    r = circle[2]

    x1 = point[0] - x_c
    y1 = point[1] - y_c
    x2 = point[2] - x_c
    y2 = point[3] - y_c


    point_r1 = x1**2 + y1**2
    point_r2 = x2**2 + y2**2


    if point_r1 < r**2 < point_r2 or point_r2 < r**2 < point_r1: return True
    else: return False




n_x = int(input())


for j in range(n_x):
    ret = 0
    point = list(map(int, input().split())) # x1, y1, x2, y2

    n_c = int(input())

    
    for i in range(n_c):
        circle = list(map(int,input().split())) # x_c, y_c, r
        if check_circle(circle, point):
            ret += 1
    print(ret)
```

재밌는 문제였다.  
복잡해 보이지만 핵심만 알면 그렇게 어려운 문제는 아니였다.  
문제의 핵심 조건은 아래와 같다.
> 행성계의 경계가 맞닿거나 서로 교차하는 경우는 없다. 또한, 출발점이나 도착점이 행성계 경계에 걸쳐진 경우 역시 입력으로 주어지지 않는다.

즉, 행성계의 진입/이탈이 필요한 순간은 딱 두가지 밖에 없다.
1. 시작점이 원 안에 있으며 도착점은 원 밖에 있는 경우
2. 시작점이 원 밖에 있으며 도착점은 원 안에 있는 경우

그 외에 시작점 도착점 둘 다 원 밖에 있다면 행성 진입/이탈이 이루어지지 않으며
둘 다 원 안에 있더라도 마찬가지다.

위 조건을 기억한채 문제를 풀면 어렵지 않다.


나같은 경우 좌표계를 이용하면 복잡할듯 하여
모든 좌표계를 원의 중심이 (0,0)으로 오도록 정렬한 뒤
* 원의 반지름
* (0,0)에서 시작점까지의 거리
* (0,0)에서 도착점까지의 거리

위 세가지를 대소비교 해주는 함수를 만들음으로써 행성을 진입/이탈 하였는지 파악하였다.

그리고 이 부분이 해당 문제의 핵심이다.
