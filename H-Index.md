H-Index

```python
# citations = [3, 0, 6, 1, 5]
# citations = [1, 7, 0, 1, 6, 4]
citations = [14, 15]

count = 0
citations = sorted(citations)
n = len(citations)


for p, q in enumerate(citations):
    if q >= n and n - p <= q:
        count += 1
    else:
        n -= 1
print(count)
```

