### BFS와 DFS

---

```PYTHON
import sys
input = sys.stdin.readline
sys.setrecursionlimit(10000)

from collections import deque

def dfs(x):
    ans.append(x)
    visit[x] = 1
    for i in adj[x]:
        if not visit[i]:
            dfs(i)
    return

def bfs(x):
    queue = deque()
    queue.append(x)
    while queue:
        # print('hi')
        y = queue.popleft()
        if not visit2[y]:
            visit2[y] = 1
            ans2.append(y)
            for a in adj[y]:
                if not visit2[a]:
                    queue.append(a)
    return

N, M, V = map(int, input().split())
adj = {x:[] for x in range(N+1)}
# print(adj)
for i in range(M):
    x, y = map(int, input().split())
    adj[x].append(y)
    adj[y].append(x)
# print(adj)
ans = []
ans2 = []

for a in adj:
    adj[a].sort()

visit = [0 for _ in range(N + 1)]
dfs(V)
print(*ans)
visit2 = [0 for _ in range(N + 1)]
bfs(V)
print(*ans2)
```

