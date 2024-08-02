# Sort List

Problem page:[https://leetcode.com/problems/sort-list](https://leetcode.com/problems/sort-list)

## Solution

```python
class Solution:
    def sortList(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if not head or not head.next:
            return head
        slow, fast = head, head.next
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next
        mid = slow.next
        slow.next = None
        left = self.sortList(head)
        right = self.sortList(mid)

        sentinel = ListNode(0)
        cur = sentinel
        while left and right:
            if left.val < right.val:
                cur.next = left
                left = left.next
            else:
                cur.next = right
                right = right.next
            cur = cur.next
        cur.next = left or right
        return sentinel.next
```

## Complexity

- time: O(n \* log n)
- space: O(log n)
