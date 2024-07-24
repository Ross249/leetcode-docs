# Remove Duplicates from Sorted List II

Problem page:[https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii)

## Solution

```python
class Solution:
    def deleteDuplicates(self, head: Optional[ListNode]) -> Optional[ListNode]:

        sentinel = ListNode(0)
        sentinel.next = head
        pre,cur = sentinel,head

        while cur:

            while cur.next and cur.val == cur.next.val:
                cur = cur.next
            if pre.next == cur:
                pre = pre.next
                cur = cur.next
            else:
                pre.next = cur.next
                cur = pre.next
        return sentinel.next
```

## Complexity

- time: O(n)
- space: O(1)
