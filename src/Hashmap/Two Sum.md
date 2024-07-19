# Two Sum

Problem page:[https://leetcode.com/problems/two-sum](https://leetcode.com/problems/two-sum)

## Solution

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        collect = {}
        n = len(nums)

        for i in range(n):
            left = target - nums[i]
            if left in collect:
                return [collect[left],i]
            collect[nums[i]] = i

        return []
```

## Complexity

- time: O(n)
- space: O(n)
