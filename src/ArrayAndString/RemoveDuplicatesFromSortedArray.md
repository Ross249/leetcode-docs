# Remove Duplicates from Sorted Array

Problem page:[https://leetcode.com/problems/remove-duplicates-from-sorted-array](https://leetcode.com/problems/remove-duplicates-from-sorted-array)

## Solution

```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        res = 1
        for i in range(1, len(nums)):
            if nums[i] != nums[i-1]:
                nums[res] = nums[i]
                res += 1
        return res
```

## Complexity

- time: O(n)
- space: O(1)
