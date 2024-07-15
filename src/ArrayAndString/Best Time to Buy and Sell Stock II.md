# Best Time to Buy and Sell Stock II

Problem page:[https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-ii)

## Solution

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        max = 0
        start = prices[0]
        len1 = len(prices)
        for i in range(0 , len1):
            if start < prices[i]:
                max += prices[i] - start
            start = prices[i]
        return max
```

## Complexity

- time: O(n)
- space: O(1)
