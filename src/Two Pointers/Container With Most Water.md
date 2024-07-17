# Container With Most Water

Problem page:[https://leetcode.com/problems/container-with-most-water](https://leetcode.com/problems/container-with-most-water)

## Solution

```python
class Solution:
    def maxArea(self, height: List[int]) -> int:
        l, r, area = 0, len(height) - 1, 0
        while l < r:
            temp_area = (r - l) * min(height[l], height[r])
            area = max(temp_area,area)
            if height[l] < height[r]:
                l += 1
            else:
                r -= 1
        return area
```

## Complexity

- time: O(n)
- space: O(1)
