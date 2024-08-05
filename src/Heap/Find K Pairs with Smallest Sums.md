# Find K Pairs with Smallest Sums

Problem page:[https://leetcode.com/problems/find-k-pairs-with-smallest-sums](https://leetcode.com/problems/find-k-pairs-with-smallest-sums)

## Solution

```python
class Solution:
    def kSmallestPairs(self, nums1: List[int], nums2: List[int], k: int) -> List[List[int]]:
        res = []
        pq = []
        for num in nums1:
            heapq.heappush(pq,[num + nums2[0], 0])
        print(pq)
        while k > 0 and pq:
            pair = heapq.heappop(pq)
            small, pos = pair[0], pair[1]
            res.append([small - nums2[pos],nums2[pos]])
            if pos + 1 < len(nums2):
                heapq.heappush(pq,[small - nums2[pos] + nums2[pos + 1], pos + 1])
            k -= 1
        return res
```

## Complexity

- time: O(k \* log(n1))
- space: O(n1 + k)
