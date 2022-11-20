# 백준 15904번 - 'UCPC는 무엇의 약자일까?' (실버5)

```
from collections import deque
words = list(input())
words = deque(words)


ucpc = deque(["U", "C", "P", "C"])


while words:
    word = words.popleft()
    if word == ucpc[0]: ucpc.popleft()
    if not ucpc: break

if ucpc: print("I hate UCPC")
else: print("I love UCPC")
```

그리디 알고리즘 문제.  
그리디 알고리즘 문제에서 나는 큐를 즐겨 쓰는거 같다.  
이 문제 역시 큐로 풀 수 있다.  

문제는 어렵지 않다.  