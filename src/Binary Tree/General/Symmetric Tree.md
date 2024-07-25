# Symmetric Tree

Problem page:[https://leetcode.com/problems/symmetric-tree](https://leetcode.com/problems/symmetric-tree)

## Solution

```python
class Solution:
    def helper(self, left: TreeNode, right:TreeNode)->bool:
        if not left and not right:
            return True
        if not left or not right:
            return False
        return (left.val == right.val) and self.helper(left.left, right.right) and self.helper(left.right, right.left)
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        return self.helper(root,root)
```

## Complexity

- time: O(n)
- space: O(h)
