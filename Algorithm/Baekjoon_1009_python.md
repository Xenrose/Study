# 백준 1009번 - 분산처리

```
n = int(input())

for i in range(n):
    a, b = map(int, input().split())
    temp = []
    for i in range(1,20):
        t = str(a**i)[-1]
        if t == "0": t = "10"
        if int(t) in temp: pass
        else: temp.append(int(t))

    answer = temp[(b%len(temp))-1]
    print(answer)
```

생각보다 까다로운 문제  

답을 그냥 단순히 `(a**b)%10` 으로 한다면 두가지 문제에 직면한다.

1. 시간초과 - 제곱수가 많아지면서 계산시간이 제한시간을 초과해버리는것
2. 끝자리가 0일 경우 - 가령 a = 100, b = 1일 경우 `(a**b)%10 == 0`이 나오게 된다. 하지만 답은 '10'이여야 한다.  

이 문제에서 주목할 점은 바로 ***마지막 자리수가 몇이냐*** 이다.  
그리고 이는 따로 제곱수를 계속해서 하다보면 일정한 패턴으로 반복된다는 점을 알 수 있다.  
즉, a와 b가 각각 아주 커다란 숫자라면 이를 계산하는데 시간이 오래 소요되지만  
***끝자리가 같은 패턴으로 반복한다는 사실을 안다면*** 해당 패턴을 list로 만들어서  
우리는 마지막 숫자가 몇이 올지 예측할 수 있다.  

마지막 수의 패턴을 찾기 위해 일단 for문으로 약 20번 정도 제곱을 해준다. (10번 정도만 해도 무관하다)  
이후 str로 변환하여 마지막 숫자만 list에 담아준다.  
단, 이때 두가지를 주의해야한다.  
* 만약 넣으려는 수가 이미 list에 있을땐 pass
* 만약 넣으려는 수가 '0'이라면 '10'으로 변환하여 넣는다.

이제 나머지는 그저 b를 list의 길이(패턴의 길이)를 나눠주기만 하면 된다.  
나눈 뒤 나온 숫자가 n일 경우 패턴의 n번째 숫자가 마지막 숫자이기에  
list[n-1]을 답으로 선언하면 정답이 된다.  
