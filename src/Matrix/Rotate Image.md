# Rotate Image

Problem page:[https://leetcode.com/problems/rotate-image](https://leetcode.com/problems/rotate-image)

## Solution

```python
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        n = len(matrix)
        top, bottom = 0, n - 1
        while top < bottom:
            for col in range(n):
                temp = matrix[top][col]
                matrix[top][col] = matrix[bottom][col]
                matrix[bottom][col] = temp
            top += 1
            bottom -= 1

        for r in range(n):
            for c in range(r + 1, n):
                temp = matrix[r][c]
                matrix[r][c] = matrix[c][r]
                matrix[c][r] = temp

        return matrix
```

## Complexity

- time: O(n^2)
- space: O(1)
