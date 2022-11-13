# 백준 2810번 - '컵홀더' (브론즈1)

```
n = int(input())

chair = input()

if "LL" in chair:
    chair = chair.replace("LL","S")


cup_holder = chair.count("S") + 1

if cup_holder >= n:
    print(n)
else:
    print(cup_holder)
```

그리디 알고리즘 문제.  
문자열에 대해 기본지식을 가지고 있다면  
어렵지 않게 쉽게 해결할 수 있다.  
