# Copy List with Random Pointer

Problem page:[https://leetcode.com/problems/copy-list-with-random-pointer](https://leetcode.com/problems/copy-list-with-random-pointer)

## Solution

```python
def copyRandomList(self, head: 'Optional[Node]') -> 'Optional[Node]':
        if not head:
            return None
        res = {}
        cur = head
        while cur:
            res[cur] = Node(cur.val)
            cur = cur.next
        cur = head
        while cur:
            res[cur].next = res.get(cur.next)
            res[cur].random = res.get(cur.random)
            cur = cur.next
        return res[head]
```

## Complexity

- time: O(n)
- space: O(1)
