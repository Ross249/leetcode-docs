# Kth Smallest Element in a BST

Problem page:[https://leetcode.com/problems/kth-smallest-element-in-a-bst](https://leetcode.com/problems/kth-smallest-element-in-a-bst)

## Solution

```python
class Solution:
    def kthSmallest(self, root: Optional[TreeNode], k: int) -> int:
        res = []

        def helper(node:Optional[TreeNode]):
            if node is None:
                return
            helper(node.left)
            res.append(node.val)
            helper(node.right)
        helper(root)
        return res[k-1]
```

## Complexity

- time: O(n)
- space: O(n)
