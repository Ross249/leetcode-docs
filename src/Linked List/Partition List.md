# Partition List

Problem page:[https://leetcode.com/problems/partition-list](https://leetcode.com/problems/partition-list)

## Solution

```python
class Solution:
    def partition(self, head: Optional[ListNode], x: int) -> Optional[ListNode]:
        sHead,lHead = ListNode(0), ListNode(0)
        s, l = sHead, lHead
        while head is not None:
            if head.val < x:
                s.next = head
                s = s.next
            else:
                l.next = head
                l = l.next
            head = head.next
        s.next = lHead.next
        l.next = None
        return sHead.next
```

## Complexity

- time: O(n)
- space: O(1)
