# Word Search II

Problem page:[https://leetcode.com/problems/word-search-ii](https://leetcode.com/problems/word-search-ii/)

## Solution

```python
class TreeNode:
    def __init__(self):
        self.children = {}
        self.isWord = False
        self.refs = 0
    def addWord(self, word):
        cur = self
        cur.refs += 1
        for letter in word:
            if letter not in cur.children:
                cur.children[letter] = TreeNode()
            cur = cur.children[letter]
            cur.refs += 1
        cur.isWord = True
    def removeWord(self, word):
        cur = self
        cur.refs -= 1
        for letter in word:
            if letter in cur.children:
                cur = cur.children[letter]
                cur.refs -= 1

class Solution:
    def findWords(self, board: List[List[str]], words: List[str]) -> List[str]:
        root = TreeNode()
        for w in words:
            root.addWord(w)

        r,c = len(board), len(board[0])

        res, visit = set(), set()

        def dfs(row, col, node, word):
            if row not in range(r) or col not in range(c) or board[row][col] not in node.children or node.children[board[row][col]].refs < 1 or (row,col) in visit:
                return
            visit.add((row,col))

            node = node.children[board[row][col]]
            word += board[row][col]
            if node.isWord:
                node.isWord = False
                res.add(word)
                root.removeWord(word)
            dfs(row + 1, col, node, word)
            dfs(row - 1, col, node, word)
            dfs(row , col + 1, node, word)
            dfs(row , col - 1, node, word)
            visit.remove((row,col))

        for row in range(r):
            for col in range(c):
                dfs(row,col,root,"")
        return list(res)
```

## Complexity

- time: O( m+n.(4^k) ) m is the number of letters in words, n is the number of letters on board, k is the max length of words or the depth of tree, 4 is the 4 directions
- space: O(n \* m)
