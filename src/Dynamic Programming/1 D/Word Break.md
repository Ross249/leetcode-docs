# Word Break

Problem page:[https://leetcode.com/problems/word-break](https://leetcode.com/problems/word-break)

## Solution

```python
class Solution:
    def wordBreak(self, s: str, wordDict: List[str]) -> bool:
        dp = [True] + [False] * len(s)
        for i in range(1, len(s) + 1):
            for w in wordDict:
                start = i - len(w)
                if start >= 0 and dp[start] and s[start:i] == w:
                    dp[i] = True
                    break
        return dp[-1]
```

## Complexity

- time: O(n \* m \* k) n is length of input string, m is number of words in wordDict, k is average size of substrings
- space: O(n)
