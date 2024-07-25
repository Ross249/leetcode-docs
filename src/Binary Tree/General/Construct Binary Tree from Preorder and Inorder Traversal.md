# Construct Binary Tree from Preorder and Inorder Traversal

Problem page:[https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal)

## Solution

```python
class Solution:
    def __init__(self):
        self.p = 0
        self.i = 0
    def buildTree(self, preorder: List[int], inorder: List[int]) -> Optional[TreeNode]:
        def helper(stop):
            if self.i < len(inorder) and inorder[self.i] != stop:
                root = TreeNode(preorder[self.p])
                self.p += 1
                root.left = helper(root.val)
                self.i += 1
                root.right = helper(stop)
                return root
            return None
        return helper(None)
```

## Complexity

- time: O(n)
- space: O(n)
