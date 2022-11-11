# 백준 15720번 - '카우버거' (실버5)

```
b, c, d = map(int,input().split())

burger = list(map(int,input().split()))
side = list(map(int,input().split()))
drink = list(map(int,input().split()))

burger.sort(reverse=True)
side.sort(reverse=True)
drink.sort(reverse=True)

# 세트할인 10%


no_sale = sum(burger) + sum(side) + sum(drink)
print(no_sale)

set_menu = min(b,c,d)

sale = 0
sale += sum(burger[i]*0.9 if set_menu >= 1+i else burger[i] for i in range(len(burger)))
sale += sum(side[i]*0.9 if set_menu >= 1+i else side[i] for i in range(len(side)))
sale += sum(drink[i]*0.9 if set_menu >= 1+i else drink[i] for i in range(len(drink)))

print(int(sale))
```

그리디 알고리즘 문제  
list comprehension 내에 if else 구문을 넣을 수 있다면
아주 쉽고 간결하게 코드를 짤 수 있다.  