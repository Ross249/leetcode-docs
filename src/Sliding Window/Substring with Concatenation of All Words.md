# Substring with Concatenation of All Words

Problem page:[https://leetcode.com/problems/substring-with-concatenation-of-all-words](https://leetcode.com/problems/substring-with-concatenation-of-all-words)

## Solution

```python
class Solution:
    def findSubstring(self, s: str, words: List[str]) -> List[int]:
        if not s or not words:
            return []
        word_len, num_words = len(words[0]), len(words)
        word_count = Counter(words)
        res = []

        for i in range(word_len):
            l, r, count = i, i, 0
            seen = defaultdict(int)

            while r + word_len <= len(s):
                word = s[r:r+word_len]
                r += word_len
                if word in word_count:
                    seen[word] += 1
                    count += 1

                    while seen[word] > word_count[word]:
                        l_word = s[l:l + word_len]
                        seen[l_word] -= 1
                        count -= 1
                        l += word_len
                    if count == num_words:
                        res.append(l)
                else:
                    seen.clear()
                    count = 0
                    l = r
        return res
```

## Complexity

- time: O(n \* m), where n is the length of s and m is the length of each word
- space: O(k), where k is the number of unique words in the words list
