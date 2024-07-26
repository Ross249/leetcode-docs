# Sum Root to Leaf Numbers

Problem page:[https://leetcode.com/problems/sum-root-to-leaf-numbers](https://leetcode.com/problems/sum-root-to-leaf-numbers)

## Solution

```python
class Solution:
    def sumNumbers(self, root: Optional[TreeNode]) -> int:
        def helper(node,num):
            if not node:
                return 0
            num = 10 * num + node.val
            if not node.left and not node.right:
                return num
            return helper(node.left,num) + helper(node.right, num)
        return helper(root, 0)
```

## Complexity

- time: O(n)
- space: O(h)
