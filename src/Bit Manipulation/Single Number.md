# Single Number

Problem page:[https://leetcode.com/problems/single-number](https://leetcode.com/problems/single-number)

## Solution

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        res = 0
        for num in nums:
            res ^= num
        return res
```

## Complexity

- time: O(n)
- space: O(1)
