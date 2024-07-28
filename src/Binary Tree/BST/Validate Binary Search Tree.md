# Validate Binary Search Tree

Problem page:[https://leetcode.com/problems/validate-binary-search-tree](https://leetcode.com/problems/validate-binary-search-tree)

## Solution

```python
class Solution:
    def isValidBST(self, root: Optional[TreeNode]) -> bool:
        def helper(node,min_val, max_val):
            if not node:
                return True
            if (min_val is not None and node.val <= min_val) or (max_val is not None and node.val >= max_val):
                return False
            return helper(node.left, min_val, node.val) and helper(node.right, node.val, max_val)
        return helper(root,-sys.maxsize,sys.maxsize)
```

## Complexity

- time: O(n)
- space: O(1)
