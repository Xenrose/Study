# 백준 18238번 - 'ZOAC 2' (브론즈2)

```
from collections import deque

def roll(target,deque=deque):
    cnt = 0
    while True:
        if deque[0] == target: return cnt, deque
        
        deque.append(deque.popleft())
        cnt += 1



alpabat = [chr(i) for i in range(65,91)]
alpabat = deque(alpabat)

words = input()

answer = 0
cnt = 0

for i in words:
    cnt, alpabat = roll(i,alpabat)
    cnt = min(26-cnt,cnt)
    answer += cnt

print(answer)

```

그리디 알고리즘 문제.  
큐를 이용해서 풀면 쉽게 풀 수 있다.  
주의할 점은 왼쪽으로 돌렸을 경우 카운트를 어떻게 구현하냐 인데  
이는 알파벳의 갯수 26개를 빼줌으로써 해결했다.
