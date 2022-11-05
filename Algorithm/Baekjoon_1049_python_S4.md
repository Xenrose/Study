# 백준 1049번 - 기타줄 (실버4)

```
n, m = map(int,input().split())

pack = []
single = []

ret = []

for i in range(m):
    p, s = map(int, input().split())
    pack.append(p)
    single.append(s)


pack_min = min(pack)
single_min = min(single)

ret.append(((n//6)+1)*pack_min)
ret.append(n*single_min)

temp = ((n//6))*pack_min + (n%6)*single_min
ret.append(temp)


print(min(ret))
```

그렇게 어려운 문제는 아니였다.  
복잡해보일지언정 차분히 생각하면 아주 쉽게 풀리는 문제.  

그저 가장 저렴한것만 구매하면 되기에
1. 패키지로만 살 경우
2. 낱개로만 살 경우
3. 패키지+낱개로 살 경우

세가지 경우의 수를 전부 가격을 계산하여 하나의 list에 넣고  
min(list)를 통해 출력된 값을 정답으로 입력하면 된다.
