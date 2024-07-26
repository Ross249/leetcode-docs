# Binary Tree Maximum Path Sum

Problem page:[https://leetcode.com/problems/binary-tree-maximum-path-sum](https://leetcode.com/problems/binary-tree-maximum-path-sum)

## Solution

```python
class Solution:
    def _max(self, root):
        if not root: return -sys.maxsize
        l = max(0, self._max(root.left))
        r = max(0, self._max(root.right))
        self.res = max(self.res, root.val + l + r)
        return root.val + max(l, r)
    def maxPathSum(self, root):
        self.res = -sys.maxsize
        self._max(root)
        return self.res
```

## Complexity

- time: O(n)
- space: O(h)
