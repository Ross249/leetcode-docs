# Minimum Number of Arrows to Burst Balloons

Problem page:[https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons](https://leetcode.com/problems/minimum-number-of-arrows-to-burst-balloons)

## Solution

```python
def findMinArrowShots(self, points: List[List[int]]) -> int:
        points.sort(key= lambda x : x[0])
        res, end = 1, points[0][1]

        for balloon in points[1:]:
            if balloon[0] > end:
                res += 1
                end = balloon[1]
            else:
                end = min(end, balloon[1])
        return res
```

## Complexity

- time: O(n)
- space: O(1)
