# Maximum Subarray

Problem page:[https://leetcode.com/problems/maximum-subarray](https://leetcode.com/problems/maximum-subarray)

## Solution

```python
class Solution:
    def maxSubArray(self, nums: List[int]) -> int:
        res,cur = nums[0], nums[0]
        for num in nums[1:]:
            cur = max(num, cur + num)
            res = max(res, cur)
        return res
```

## Complexity

- time: O(n)
- space: O(1)
