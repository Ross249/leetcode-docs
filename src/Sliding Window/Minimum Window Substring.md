# Minimum Window Substring

Problem page:[https://leetcode.com/problems/minimum-window-substring](https://leetcode.com/problems/minimum-window-substring)

## Solution

```python
class Solution:
    def minWindow(self, s: str, t: str) -> str:
        if len(t) > len(s) or not s or not t:
            return ""
        map = [0] * 128
        count, l, r, s_idx = len(t), 0, 0, 0
        min_len = float('inf')
        for c in t:
            map[ord(c)] += 1
        while r < len(s):
            if map[ord(s[r])] > 0:
                count -= 1
            map[ord(s[r])] -= 1
            r += 1

            while count == 0:
                if r - l < min_len:
                    min_len = r - l
                    s_idx = l
                if map[ord(s[l])] == 0:
                    count += 1
                map[ord(s[l])] += 1
                l += 1
        return "" if min_len == float('inf') else s[s_idx:s_idx + min_len]
```

## Complexity

- time: O(n)
- space: O(1)
