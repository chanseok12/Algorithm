### 피보나치 수열 2(DP)

---

```python
import sys
input = sys.stdin.readline

N = int(input())
fibo = [0] * (N+1)
for i in range(N+1):
    if i == 0:
        fibo[i] = 0
    elif i == 1 or i == 2:
        fibo[i] = 1
    else:
        fibo[i] = fibo[i-1] + fibo[i-2]
print(fibo[-1])
```

