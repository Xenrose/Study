# 백준 6550번 - 부분 문자열 (실버5)

```
from collections import deque

while True:
    try:
        s, t = map(str, input().split())

        s_temp = deque(list(s))


        for i in t:
            if len(s_temp) != 0:
                if i == s_temp[0]:
                    s_temp.popleft()
            else:
                break


        if len(s_temp) == 0:
            print("Yes")
        else:
            print("No")
    except:
        break
```

정말 방심했던 문제이다.  
의외로 발상의 전환이 필요하다.  

s가 t에 속해있는지 체크하는것보다는
t의 요소가 s에 있다면 그 요소를 삭제하고
최종적으로 s의 길이를 체크하는 방법이

s가 t에 속해있는지 체크할때 빠질 함정(반례)를 피할 수 있는 방법이다.
