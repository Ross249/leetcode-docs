# Find Median from Data Stream

Problem page:[https://leetcode.com/problems/find-median-from-data-stream](https://leetcode.com/problems/find-median-from-data-stream)

## Solution

```python
class MedianFinder:

    def __init__(self):
        self.min_heap = []
        self.max_heap = []

    def addNum(self, num: int) -> None:
        heapq.heappush(self.max_heap, -1 * num)
        if (self.max_heap and self.min_heap) and -1 * self.max_heap[0] > self.min_heap[0]:
            val = -1 * heapq.heappop(self.max_heap)
            heapq.heappush(self.min_heap,val)
        if len(self.max_heap) > len(self.min_heap) + 1:
            val = -1 * heapq.heappop(self.max_heap)
            heapq.heappush(self.min_heap, val)
        elif len(self.min_heap) > len(self.max_heap) + 1:
            val = heapq.heappop(self.min_heap)
            heapq.heappush(self.max_heap, -1 * val)

    def findMedian(self) -> float:
        if len(self.max_heap) > len(self.min_heap):
            return -1 * self.max_heap[0]
        elif len(self.max_heap) < len(self.min_heap):
            return self.min_heap[0]
        else:
            return (-1 * self.max_heap[0] + self.min_heap[0]) / 2
```

## Complexity

- time: O(log n)
- space: O(n)
