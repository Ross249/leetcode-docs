# Longest Consecutive Sequence

Problem page:[https://leetcode.com/problems/longest-consecutive-sequence](https://leetcode.com/problems/longest-consecutive-sequence)

## Solution

```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        bucket = set(nums)
        res = 0
        table = {}
        for num in bucket:
            x = table.get(num - 1, 0)
            y = table.get(num + 1, 0)
            val = x + y + 1
            table[num - x] = val
            table[num + y] = val
            res = max(res, val)

        return res
```

## Complexity

- time: O(n)
- space: O(n)
