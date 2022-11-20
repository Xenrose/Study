# 백준 17262번 - '팬덤이 넘쳐흘러' (실버5)

```
import sys

n = int(sys.stdin.readline().rstrip())


frist_time = 100000 # e
end_time = 0 # s


for _ in range(n):
    s, e = map(int, sys.stdin.readline().split())
    if frist_time > e: frist_time = e
    if s > end_time: end_time = s

answer = end_time - frist_time
if 0 > answer: answer = 0

print(answer)
```

그리디 알고리즘 문제.  

해답이 바로 떠오르지 않았으나 차근차근 생각해보니 떠오르는 문제.  
frist_time = 욱제가 등교하는 시간  
end_time = 욱제가 하교하는 시간  

모든 인원과 악수를 해야 하므로  
제일 빨리 등교해서 하교하는 인원의 시간에 등교하여  
제일 늦게 등교하는 인원의 시간까지 남아있어야 최소 시간이 된다.  

이점을 유념하며 그리디 알고리즘에 맞게 해결하면 문제를 풀 수 있다.  

참고로 python 3 기준 input을 사용할 경우 시간이 4000ms가 넘어가버린다.  
sys.stdin.readline()을 사용해주면 시간을 200ms으로 줄일 수 있다.  