# Longest Palindromic Substring

Problem page:[https://leetcode.com/problems/longest-palindromic-substring](https://leetcode.com/problems/longest-palindromic-substring)

## Solution

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        n = len(s)
        dp = [[-1]*n for _ in range(n)]
        def helper(i, j):
            if dp[i][j] != -1:
                return dp[i][j] == 1
            if i >= j:
                dp[i][j] = 1
                return True
            if s[i] == s[j]:
                dp[i][j] = helper(i + 1, j - 1)
                return dp[i][j] == 1
            dp[i][j] = 0
            return False
        max_len = 0
        start = 0
        for i in range(n):
            for j in range(i, n):
                if helper(i,j):
                    if j - i + 1 > max_len:
                        max_len = j - i + 1
                        start = i
        return s[start: start + max_len]
```

## Complexity

- time: O(n \* n)
- space: O(n \* n)
