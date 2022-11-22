# 백준 2865번 - '나는 위대한 슈퍼스타K' (실버4)

```
import sys; input = sys.stdin.readline

n, m, k = map(int,input().split())


cate = [list(map(eval, input().split())) for _ in range(m)]

all_cate = []
cate_dict = dict()

for i in range(len(cate)):
    for j in range(len(cate[i])):
        all_cate.append(cate[i][j])

for i in range(n):
    temp = []
    for j in range(len(all_cate)):
        if type(all_cate[j])==int and all_cate[j] == i+1: temp.append(all_cate[j+1])
    cate_dict[i+1] = temp


answer = []
for i in range(n):
    answer.append(max(cate_dict[i+1]))

answer.sort(reverse=True)
print(round(sum(answer[:k]),1))
```

그리디 알고리즘 문제.  
코드를 최대한 깔끔하게 작성하려 했으나 조금 난잡한감이 있다.  

또한 이 문제의 함정은 '소수점 첫째자리까지 반올림해 출력한다.' 이 부분이다.  
이 부분을 무시하고 round 함수를 사용하지 않으면  
문제가 틀리게 된다.  

이거 때문에 혹시 코드가 틀린건 아닌지 다시 점검하고 바꿔보았다가.  
기존 코드에서 round 함수만 추가하여 다시 제출하니 성공하였다.  

참고로 나는 주어진 입력이 직관적이지 않아서  
2차원 list를 1차원 list로 바꾼 뒤 dictionary를 선언하여 value 값에 각 참가자들의 능력치들을 정의하였고  
맨 마지막에는 참가자들 능력치의 최대값만 담은 list를 만들어서 정답을 출력하여  
문제를 해결하였다.