# Unique Paths II

Problem page:[https://leetcode.com/problems/unique-paths-ii](https://leetcode.com/problems/unique-paths-ii)

## Solution

```python
class Solution:
    def uniquePathsWithObstacles(self, obstacleGrid: List[List[int]]) -> int:
        if not obstacleGrid or not obstacleGrid[0] or obstacleGrid[0][0] == 1:
            return 0

        m, n = len(obstacleGrid), len(obstacleGrid[0])

        pre = [0] * n
        cur = [0] * n
        pre[0] = 1

        for i in range(m):
            cur[0] = 0 if obstacleGrid[i][0] == 1 else pre[0]
            for j in range(1,n):
                cur[j] = 0 if obstacleGrid[i][j] == 1 else cur[j - 1] + pre[j]
            pre[:] = cur
        return pre[n - 1]
```

## Complexity

- time: O(m \* n)
- space: O(n)
