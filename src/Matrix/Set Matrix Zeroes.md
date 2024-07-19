# Set Matrix Zeroes

Problem page:[https://leetcode.com/problems/set-matrix-zeroes](https://leetcode.com/problems/set-matrix-zeroes)

## Solution

```python
class Solution:
    def setZeroes(self, matrix: List[List[int]]) -> None:
        rows, cols = len(matrix), len(matrix[0])
        bucket_r, bucket_c = [False] * rows, [False] * cols
        for r in range(rows):
            for c in range(cols):
                if matrix[r][c] == 0:
                    bucket_r[r] = True
                    bucket_c[c] = True
        for i, r in enumerate(bucket_r):
            if r:
                for c in range(cols):
                    matrix[i][c] = 0
        for j, c in enumerate(bucket_c):
            if c:
                for r in range(rows):
                    matrix[r][j] = 0
```

## Complexity

- time: O(n \* m)
- space: O(n + m)
