### n 진수 게임

---

```python
def solution(n, t, m, p):
    answer = ''
    l = m * t
    res = ''

    def change(x, n):
        if x == 0:
            return str(0)
        c_num = '0123456789ABCDEF'
        change_n = ''
        while x > 0:
            change_n = c_num[x % n] + change_n
            x = x // n

        return change_n

    for i in range(l):
        res += change(i, n)
    # print(res)
    for i in range(p - 1, l, m):
        answer += res[i]
    return answer


# print(solution(2, 4, 2, 1))
print(solution(16, 16, 2, 1))
print(solution(16, 16, 2, 2))
```

