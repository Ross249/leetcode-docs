# Minimum Size Subarray Sum

Problem page:[https://leetcode.com/problems/minimum-size-subarray-sum](https://leetcode.com/problems/minimum-size-subarray-sum)

## Solution

```python
def minSubArrayLen(self, target: int, nums: List[int]) -> int:
        if sum(nums) < target: return 0
        sums, l, res = 0, 0, len(nums)
        for r, val in enumerate(nums):
            sums += val
            while sums >= target:
                sums -= nums[l]
                res = min(res, r - l + 1)
                l += 1
        return res
```

## Complexity

- time: O(n)
- space: O(1)
