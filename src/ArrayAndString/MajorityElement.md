# Majority Element

Problem page:[https://leetcode.com/problems/majority-element](https://leetcode.com/problems/majority-element)

## Solution

```python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        count = 0
        res = 0
        for num in nums:
            if count == 0 and res != num:
                res = num
                count += 1
            elif res == num:
                count += 1
            else:
                count -= 1
        return res
```

## Complexity

- time: O(n)
- space: O(1)
