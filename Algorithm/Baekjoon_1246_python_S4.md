# 백준 1246번 - 온라인 판매 (실버4)

```
n, m = map(int,input().split())

price = [int(input()) for _ in range(m)]

temp_price = list(set(price))
temp_price.sort()


ret = []

for i in temp_price:
    temp_price = list(filter(lambda x: x >= i, price))
    if len(temp_price) > n:
        ret.append([i*n,i])
    else:
        ret.append([i*len(temp_price), i])

ret.sort(reverse = True)
print(ret[0][1], ret[0][0], end = ' ')


```

그닥 어렵지는 않았지만 조금은 헤맨 문제

가격 책정의 경우에는 굳이 고민할 필요 없이  
고객들이 제시한 가격으로 판매시 얼마의 수익이 나오는지에 대해  
list를 만들고 추가해가면 된다.

다만 여기서 중요한 점은 달걀의 갯수.  

이를테면 A가격으로 판매시 사겠다는 사람이 달걀의 갯수보다 더 많을 수도 있으므로  
이럴 경우에는 총 수익을 사겠다는 사람이 아닌 최대 달걀 갯수와 가격을 곱해야 한다.

1. A가격으로 판매시 구매자 보다 달걀이 많을 경우
2. A가격으로 판매시 구매자가 달걀 보다 적을 경우 

위 두가지 사례를 유념하면서 그리디 알고리즘으로 풀면 쉽게 풀린다.


여담으로 번역이 이상하게 되어서 문제 이해하는데 좀 어려웠다.  
원문을 보면 오히려 이해하기 더 쉬웠는데  
부디 번역을 이상하게 하지 않아줬으면 한다...