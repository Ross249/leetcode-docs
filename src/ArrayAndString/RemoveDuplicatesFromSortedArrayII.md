# Remove Duplicates from Sorted Array II

Problem page:[https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/)

## Solution

```python
class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        length = len(nums)
        if length <= 2:
            return length
        start = 2
        for i in range(2,length):
            if nums[i] != nums[start - 2]:
                nums[start] = nums[i]
                start += 1
        return start
```

## Complexity

- time: O(n)
- space: O(1)
