# 백준 3929번 - '패스트 푸드 상금' (브론즈1)

```
def dict_check(dict, list):
    for i in list:
        if dict[str(i)] == 0:
            return False
    
    return True

def dict_ele_down(dict, list):
    for i in list:
        dict[str(i)] -= 1

    return dict

def sep_list(list):
    list_len = list[0]
    list_ele = list[1:-1]
    list_price = list[-1]

    return list_len, list_ele, list_price



t = int(input())

for i in range(t):
    n, m = map(int,input().split())

    n_temp = [list(map(int,input().split())) for _ in range(n)]

    m_temp = list(map(int,input().split()))

    ret = dict()
    for i in range(m):
        ret[str(i+1)] = m_temp[i]



    last_price = 0
    for i in n_temp:
        len, ele, price = sep_list(i)
        while True:
            if dict_check(ret, ele):
                last_price += price
                ret = dict_ele_down(ret, ele)
            else:
                break

    print(last_price)
```

그리디 알고리즘 + 구현 문제.  

구현 문제여서 그런걸까 코드가 상당히 길다.  
이 티어에서는 보통 이렇게까지 긴 답은 안나오는거 같던데  

여튼 이 문제의 핵심은 문제를 이해하는데 있다.  
특히 입력 중 1부터 m까지 스티커의 개수를 입력 받는 부분이 있는데  
문제를 풀 당시에는 
이부분이 이해가 되지 않아서 많이 헤매었다.

예시를 통해 설명하자면
가령 m이 5일 경우
스티커의 종류는 1,2,3,4,5 이며  
1부터 m까지 스티커의 개수 입력이  
2 2 0 4 4 일때  
스티커1의 개수 = 2  
스티커2의 개수 = 2  
스티커3의 개수 = 0  
스티커4의 개수 = 4   
스티커5의 개수 = 4  
라는 의미이다.

해당 부분만 이해했다면 그 이후부터는 그리디알고리즘과 구현문제임을 기억하며 문제를 해결하면 된다.