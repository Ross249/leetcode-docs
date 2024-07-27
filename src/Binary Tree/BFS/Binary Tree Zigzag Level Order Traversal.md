# Binary Tree Zigzag Level Order Traversal

Problem page:[https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal](https://leetcode.com/problems/binary-tree-zigzag-level-order-traversal)

## Solution

```python
def zigzagLevelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        if not root:
            return []
        queue = deque([root])
        res = []
        flag = False
        while queue:
            length = len(queue)
            temp = []
            for i in range(length):
                node = queue.popleft()
                temp.append(node.val)
                if node.left:
                    queue.append(node.left)
                if node.right:
                    queue.append(node.right)
            if flag:
                temp = temp[::-1]

            res.append(temp)
            flag = not flag

        return res
```

## Complexity

- time: O(n)
- space: O(d)
