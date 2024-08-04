# Search a 2D Matrix

Problem page:[https://leetcode.com/problems/search-a-2d-matrix](https://leetcode.com/problems/search-a-2d-matrix)

## Solution

```python
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        if not matrix:
            return False
        m, n = len(matrix), len(matrix[0])
        left, right = 0, m * n - 1

        while left <= right:
            mid = (left + right) // 2
            mid_row, mid_col = divmod(mid, n)

            if matrix[mid_row][mid_col] == target:
                return True
            elif matrix[mid_row][mid_col] < target:
                left = mid + 1
            else:
                right = mid - 1

        return False
```

## Complexity

- time: O(log(m\*n))
- space: O(1)
