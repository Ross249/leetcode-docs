# Spiral Matrix

Problem page:[https://leetcode.com/problems/spiral-matrix](https://leetcode.com/problems/spiral-matrix)

## Solution

```python
class Solution:
    def spiralOrder(self, matrix: List[List[int]]) -> List[int]:
        rows, cols = len(matrix), len(matrix[0])

        row, col = 0, -1

        direction = 1

        res = []

        while rows > 0 and cols > 0:
            for _ in range(cols):
                col += direction
                res.append(matrix[row][col])
            rows -= 1
            for _ in range(rows):
                row += direction
                res.append(matrix[row][col])
            cols -= 1

            direction *= -1
        return res
```

## Complexity

- time: O(m \* n)
- space: O(m \* n)
