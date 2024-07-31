# Implement Trie (Prefix Tree)

Problem page:[https://leetcode.com/problems/implement-trie-prefix-tree](https://leetcode.com/problems/implement-trie-prefix-tree)

## Solution

```python
class Trie:

    def __init__(self):
        self.data = set()
        self.pref = set()

    def insert(self, word: str) -> None:
        cur = ''
        for letter in word:
            cur += letter
            self.pref.add(cur)
        self.data.add(word)

    def search(self, word: str) -> bool:
        return word in self.data

    def startsWith(self, prefix: str) -> bool:
        return prefix in self.pref
```

## Complexity

- time: O(n) O(1)
- space: O(n \* m) n is the number of words, m is the length of words
