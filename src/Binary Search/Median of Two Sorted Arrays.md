# Median of Two Sorted Arrays

Problem page:[https://leetcode.com/problems/median-of-two-sorted-arrays](https://leetcode.com/problems/median-of-two-sorted-arrays)

## Solution

```python
class Solution:
    def findMedianSortedArrays(self, nums1: List[int], nums2: List[int]) -> float:
        if len(nums1) > len(nums2):
            nums1, nums2 = nums2, nums1
        m,n = len(nums1), len(nums2)
        low, high = 0, m
        while low <= high:
            position_x = (low + high) // 2
            position_y = (m + n + 1) // 2 - position_x

            max_x = -sys.maxsize if position_x == 0 else nums1[position_x - 1]
            max_y = -sys.maxsize if position_y == 0 else nums2[position_y - 1]
            min_x = sys.maxsize if position_x == m else nums1[position_x]
            min_y = sys.maxsize if position_y == n else nums2[position_y]

            if max_x <= min_y and max_y <= min_x:
                if (m + n) % 2 == 0:
                    return (max(max_x,max_y) + min(min_x, min_y)) / 2
                else:
                    return max(max_x,max_y)
            elif max_x > min_y:
                high = position_x - 1
            else:
                low = position_x + 1
```

## Complexity

- time: O(log(min(m, n)))
- space: O(1)
