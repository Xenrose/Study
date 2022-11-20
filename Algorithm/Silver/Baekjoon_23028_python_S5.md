# 백준 23028번 - '5학년은 다니기 싫어요' (실버5)

```
n, a, b = map(int,input().split())
b -= a
class_list = [list(map(int,input().split())) for _ in range(10)]

for i in range(8-n):
    major = class_list[i][0]
    non_major = class_list[i][1]

    possible_point = 6-major
    if possible_point >= non_major: possible_point = non_major

    a += 3*major
    b += 3*possible_point

if a >= 66 and a+b >= 130: print("Nice")
else: print("Nae ga wae")
```

그리디 알고리즘 문제.  
딱히 어려운 문제가 아니다.  
전공점수를 꼭 66점까지만 채울 필요 없다는것을 기억하면서  
일단 전공수업 다 듣고 나머지는 비전공수업을 듣되  
반드시 학기당 6과목 이상만 안들으면 된다.  
