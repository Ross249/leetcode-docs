# Word Ladder

Problem page:[https://leetcode.com/problems/word-ladder](https://leetcode.com/problems/word-ladder)

## Solution

```python
class Solution:
    def ladderLength(self, beginWord: str, endWord: str, wordList: List[str]) -> int:
        if endWord not in wordList or not endWord or not beginWord or not wordList:
            return 0
        n = len(beginWord)
        dicts = defaultdict(list)
        for word in wordList:
            for i in range(n):
                dicts[word[:i] + '*' + word[i+1:]].append(word)
        queue = deque([(beginWord, 1)])
        visited = set()
        visited.add(beginWord)
        while queue:
            cur, level = queue.popleft()
            for i in range(n):
                mediate = cur[:i] + '*' + cur[i+1:]
                for word in dicts[mediate]:
                    if word == endWord:
                        return level + 1
                    if word not in visited:
                        visited.add(word)
                        queue.append((word,level+1))
        return 0
```

## Complexity

- time: O(N \* M^2) N is the number of words in wordList, and M is the length of each word.
- space: O(N \* M^2)
