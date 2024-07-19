# Spiral Matrix II

Problem page:[https://leetcode.com/problems/spiral-matrix-ii](https://leetcode.com/problems/spiral-matrix-ii)

## Solution

```python
class Solution:
    def generateMatrix(self, n: int) -> List[List[int]]:
        if n == 1:
            return [[1]]
        rows, cols = n, n
        res = [[0 for _ in range(n)] for i in range(n)]
        direction, start = 1, 1
        row, col = 0, -1
        while rows > 0 and cols > 0:
            for _ in range(cols):
                col += direction
                res[row][col] = start
                start += 1
            rows -= 1
            for _ in range(rows):
                row += direction
                res[row][col] = start
                start += 1
            cols -= 1

            direction *= -1
        return res
```

## Complexity

- time: O(n^2)
- space: O(n^2)
