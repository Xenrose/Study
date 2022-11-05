# 백준 1343번 - 폴리오미노 (실버5)

```
n = input()

n = n.replace("X","B")
n = n.replace("BBBB","AAAA")


if n.count("B") == n.count("BB")*2:
    print(n)
else:
    print("-1")
```

쉬운 문제

핵심은 다 덮을 수 없는 경우인데  
이런 경우 전체 문장에서 "B"의 갯수와 "BB"의 갯수의 두배가 같다는 조건 외에는  
전부 덮을 수 없는것으로 간주하면 된다.