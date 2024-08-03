# Maximum Sum Circular Subarray

Problem page:[https://leetcode.com/problems/maximum-sum-circular-subarray](https://leetcode.com/problems/maximum-sum-circular-subarray)

## Solution

```python
class Solution:
    def maxSubarraySumCircular(self, nums: List[int]) -> int:
        total,cur_max,cur_min = 0,0,0
        max_sum, min_sum = -sys.maxsize-1,sys.maxsize
        for num in nums:
            total += num
            cur_max = max(cur_max + num,num)
            cur_min = min(cur_min + num, num)
            max_sum = max(max_sum,cur_max)
            min_sum = min(cur_min, min_sum)

        return max_sum if max_sum < 0 else max(max_sum, total - min_sum)
```

## Complexity

- time: O(n)
- space: O(1)
