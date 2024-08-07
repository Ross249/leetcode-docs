# Factorial Trailing Zeroes

Problem page:[https://leetcode.com/problems/factorial-trailing-zeroes](https://leetcode.com/problems/factorial-trailing-zeroes)

## Solution

```python
class Solution:
    def trailingZeroes(self, n: int) -> int:
        res = 0
        i = 5
        while n / i:
            count = n // i
            res += count
            i = i * 5
        return res
```

## Complexity

- time: O(log n)
- space: O(1)
