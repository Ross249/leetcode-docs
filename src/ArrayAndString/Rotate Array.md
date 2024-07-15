# Rotate Array

Problem page:[https://leetcode.com/problems/rotate-array](https://leetcode.com/problems/rotate-array)

## Solution

```python
class Solution:
    def rotate(self, nums: List[int], k: int) -> None:
        k = k % len(nums)
        nums[:] = nums[-k:] + nums[:-k]
        return nums
```

## Complexity

- time: O(n)
- space: O(n)
