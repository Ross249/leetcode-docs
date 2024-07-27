# Binary Tree Right Side View

Problem page:[https://leetcode.com/problems/binary-tree-right-side-view](https://leetcode.com/problems/binary-tree-right-side-view)

## Solution

```python
class Solution:
    def rightSideView(self, root: Optional[TreeNode]) -> List[int]:
        res = []
        if not root:
            return res
        queue = deque([root])
        while queue:
            length = len(queue)
            for i in range(length):
                node = queue.popleft()
                if i == length - 1:
                    res.append(node.val)
                if node.left:
                    queue.append(node.left)
                if node.right:
                    queue.append(node.right)
        return res
```

## Complexity

- time: O(n)
- space: O(d)
