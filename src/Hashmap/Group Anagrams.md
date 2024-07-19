# Group Anagrams

Problem page:[https://leetcode.com/problems/group-anagrams](https://leetcode.com/problems/group-anagrams)

## Solution

```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        res = defaultdict(list)
        for word in strs:
            s_word = ''.join(sorted(word))
            res[s_word].append(word)

        return list(res.values())
```

## Complexity

- time: O(n \* k log k), where n is the number of strings and k is the maximum length of a string
- space: O(n \* k)
