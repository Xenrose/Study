# 백준 25644번 - '최대 상승' (실버5)

```
n = int(input())
n_list = list(map(int,input().split()))

ret = [0]
temp = n_list[0]
for i in range(1, n):
    if n_list[i-1] > n_list[i] and temp > n_list[i]: temp = n_list[i]
    elif n_list[i-1] <= n_list[i]: ret.append(n_list[i]-temp)

print(max(ret))
```

그리디 알고리즘 문제.  

시간 초과 때문에 조금 헤매었지만 차근차근 생각해보면 제법 쉽게 풀 수 있는 문제이다.  


먼저 n_list[0]을 temp에 정의한 뒤 반복문을 사용한다.  
  
n_list 요소를 하나씩 꺼내어 바로 이전 요소와 현재 요소의 대소관계를 비교한다.  
만약 n_list[i]가 n_list[i-1]보다 더 작으며 temp 보다도 더 작다면  
n_list[i]가 현재까지 가장 최소값이라는 의미 이므로 temp에 n_list[i]를 정의한다.  
  
만약 n_list[i-1]보다 n_list[i]가 더 크다면   
현재까지 최소값인 temp와 n_list[i]의 차이를 ret list에 추가한다.   

위 과정을 n_list 전체 조사를 한 뒤  
ret list에서 최대값을 출력하면 이것이 최대 이익이 된다.  

만약 이익을 얻지 못할 경우 ret에 최초로 추가된 [0]이 최대값이 되므로  
'0'이 출력된다.  