### 연구소(PyPy3)

---

```python
import sys
sys.stdin = open('Q1.txt', 'r')

from collections import deque

def search(w):
    global ans
    if w == 3:
        visit = [[0] * M for _ in range(N)]
        # print(virus)
        q = deque(virus[:])
        # print(virus)
        for i, j in virus:
            visit[i][j] = 1

        dx = [-1, 1, 0, 0]
        dy = [0, 0, -1, 1]

        while len(q):
            cx, cy = q.popleft()
            for d in range(4):
                nx, ny = cx + dx[d], cy + dy[d]
                if 0 <= nx < N and 0 <= ny < M and not visit[nx][ny]:
                    if board[nx][ny] == 0:
                        visit[nx][ny] = 1
                        q.append((nx, ny))
        # print(virus)
        cnt = 0
        for i in range(N):
            for j in range(M):
                if board[i][j] == 0 and not visit[i][j]:
                    cnt += 1
        ans = max(ans, cnt)
        return
    for i in range(N):
        for j in range(M):
            if board[i][j] == 0:
                board[i][j] = 1
                search(w + 1)
                board[i][j] = 0


for t in range(1, int(input())+1):
    N, M = map(int, input().split())
    board = [list(map(int, input().split())) for _ in range(N)]
    virus = []
    for i in range(N):
        for j in range(M):
            if board[i][j] == 2:
                virus.append((i, j))
    
    ans = float('-inf')
    search(0)
    print(ans)

```

