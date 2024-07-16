# Jump Game II

Problem page:[https://leetcode.com/problems/jump-game-ii](https://leetcode.com/problems/jump-game-ii)

## Solution

```python
class Solution:
    def jump(self, nums: List[int]) -> int:
        step, end, dp = 0, 0, 0
        for i in range(len(nums)-1):
            dp = max(dp,i+nums[i])
            if i == end: # try to reach
                step += 1
                end = dp
        return step
```

## Complexity

- time: O(n)
- space: O(1)
