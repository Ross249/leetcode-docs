# Triangle

Problem page:[https://leetcode.com/problems/triangle](https://leetcode.com/problems/triangle)

## Solution

```python
class Solution:
    def minimumTotal(self, triangle: List[List[int]]) -> int:
        n = len(triangle)
        for i in range(n - 2, -1, -1):
            for j in range(len(triangle[i])):
                min_sum = min(triangle[i + 1][j], triangle[i + 1][j + 1])
                cur = triangle[i][j]
                triangle[i][j] = cur + min_sum
        return triangle[0][0]
```

## Complexity

- time: O(n \* n)
- space: O(1)
