# Longest Substring Without Repeating Characters

Problem page:[https://leetcode.com/problems/longest-substring-without-repeating-characters](https://leetcode.com/problems/longest-substring-without-repeating-characters)

## Solution

```python
def lengthOfLongestSubstring(self, s: str) -> int:
        n, res, left = len(s), 0, 0
        filter_set = set()
        for r in range(n):
            if s[r] not in filter_set:
                filter_set.add(s[r])
                res = max(res, r - left + 1)
            else:
                while s[r] in filter_set:
                    filter_set.remove(s[left])
                    left += 1
                filter_set.add(s[r])
        return res
```

## Complexity

- time: O(n)
- space: O(min(m, n)) m is the length of substring
