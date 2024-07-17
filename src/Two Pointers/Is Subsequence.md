# Is Subsequence

Problem page:[https://leetcode.com/problems/is-subsequence](https://leetcode.com/problems/is-subsequence)

## Solution

```python
class Solution:
    def isSubsequence(self, s: str, t: str) -> bool:
        if len(t) < len(s):
            return False
        l1,l2 = 0, 0
        while l2 < len(t) and l1 < len(s):
            if s[l1] == t[l2]:
                l1 += 1
            l2 += 1
        return l1 == len(s)
```

## Complexity

- time: O(n)
- space: O(1)
