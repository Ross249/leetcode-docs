# Single Number II

Problem page:[https://leetcode.com/problems/single-number-ii](https://leetcode.com/problems/single-number-ii)

## Solution

```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        ones, twos = 0, 0
        for num in nums:
            ones = (ones ^ num) & ~twos
            twos = (twos ^ num) & ~ones
            print(str(ones)+",")
            print(str(twos)+"\n")
        return ones
```

## Complexity

- time: O(n)
- space: O(1)
