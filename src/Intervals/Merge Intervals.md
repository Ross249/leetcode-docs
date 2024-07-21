# Merge Intervals

Problem page:[https://leetcode.com/problems/merge-intervals](https://leetcode.com/problems/merge-intervals)

## Solution

```python
class Solution:
    def merge(self, intervals: List[List[int]]) -> List[List[int]]:
        intervals.sort(key=lambda x: x[0])
        res = [intervals[0]]
        for interval in intervals:
            if res[-1][1] < interval[0]:
                res.append(interval)
            else:
                res[-1][1] = max(res[-1][1],interval[1])
        return res
```

## Complexity

- time: O(n \* log n)
- space: O(n)
