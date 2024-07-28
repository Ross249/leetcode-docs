# Minimum Absolute Difference in BST

Problem page:[https://leetcode.com/problems/minimum-absolute-difference-in-bst](https://leetcode.com/problems/minimum-absolute-difference-in-bst)

## Solution

```python
class Solution:
    def helper(self, node:Optional[TreeNode], values:List[int]):
        if node is None:
            return
        self.helper(node.left,values)
        values.append(node.val)
        self.helper(node.right,values)

    def getMinimumDifference(self, root: Optional[TreeNode]) -> int:
        values = []
        self.helper(root,values)
        res = sys.maxsize
        for i in range(1, len(values)):
            res = min(res, values[i]-values[i-1])
        return res
```

## Complexity

- time: O(n)
- space: O(n)
