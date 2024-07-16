# Jump Game

Problem page:[https://leetcode.com/problems/jump-game](https://leetcode.com/problems/jump-game)

## Solution

```python
class Solution:
    def canJump(self, nums: List[int]) -> bool:
        value = 0
        for n in nums:
            if value < 0:
                return False
            elif n > value:
                value = n
            value -= 1
        return True
```

## Complexity

- time: O(n)
- space: O(1)
