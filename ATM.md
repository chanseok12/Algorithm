### ATM

---

```python
import sys
input = sys.stdin.readline

N = int(input())
time = list(map(int, input().split()))

ans = 0
delay = 0
time = sorted(time)
for i in range(len(time)):
    ans += time[i] + delay
    delay += time[i]

print(ans)
```

