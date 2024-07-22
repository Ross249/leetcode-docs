# Linked List Cycle

Problem page:[https://leetcode.com/problems/linked-list-cycle](https://leetcode.com/problems/linked-list-cycle)

## Solution

```python
def hasCycle(self, head: Optional[ListNode]) -> bool:
        slow, fast = head, head
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
            if fast == slow:
                return True
        return False
```

## Complexity

- time: O(n)
- space: O(1)
