### SWEA 러시아 국기 같은 깃발

---

```PYTHON
import sys
sys.stdin = open('러시아.txt', 'r')

for t in range(1, int(input())+1):
    N, M = map(int, input().split())
    flag = [input() for _ in range(N)]
    result = 2500   # 모든 칸을 전부 바꾼다면 최대 2500
    # 깃발 범위 나누기
    # 흰색 부분이 가능한 모든 부분을 반복문으로 순회
    for i in range(0, N-2):     # 최소 2칸은 남아야 하므로
        # 파란색 영역
        for j in range(i+1, N-1):
            # 각 부분의 색깔별로, 바꾸어야 할 개수 세기
            cnt = 0
            for w in range(i+1):
                for k in range(M):
                    if flag[w][k] != 'W':
                        cnt += 1
            # 파란색 몇칸 바꿔야 하는지
            for b in range(i+1, j+1):
                for k in range(M):
                    if flag[b][k] != 'B':
                        cnt += 1

            for r in range(j+1, N):
                for k in range(M):
                    if flag[r][k] != 'R':
                        cnt += 1
            if result > cnt:
                result = cnt

    print('#%d' %t, result)

```

