# 백준 14487번 - '욱제는 효도쟁이야!!' (브론즈2)

```
n = int(input())
v = list(map(int,input().split()))
print(sum(v)-max(v))
```

그리디 알고리즘 문제  
이 문제의 가장 큰 문제는 문제 설명을 너무 난해하게 했다는 점이다.  
그저 시작 마을을 선택할 수 있다는것만 더 적어줬어도  
그렇게 난해하지는 않았을거 같다  

<br>
첫번째 예제로 설명하겠다

```
5
1 6 5 2 4
```

해당 마을에는 5개의 마을이 있다.  
편의상 A, B, C, D, E 라고 칭하겠다.

그리고 두번째 줄에 있는 숫자들은 각각 아래의 값을 의미한다.  

A -> B = 1  
B -> C = 6  
C -> D = 5  
D -> E = 2  
E -> A = 4  

<br>

즉, C마을에서부터 시작했을 경우 이동비용이 가장 큰 B->C 구간을 지나지 않은채  
C마을을 시작으로 D, E, A, B 마을 전부 들릴 수 있으므로  
이동비용이 최소가 된다.
