# Remove Element

Problem page:[https://leetcode.com/problems/remove-element](https://leetcode.com/problems/remove-element)

## Solution

```python
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        length = 0
        for i in range(len(nums)):
            if nums[i] != val:
                nums[length] = nums[i]
                length += 1

        return length
```

## Complexity

- time: O(n)
- space: O(1)
