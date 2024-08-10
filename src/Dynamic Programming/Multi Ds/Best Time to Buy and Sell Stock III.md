# Best Time to Buy and Sell Stock III

Problem page:[https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iii)

## Solution

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        if not prices:
            return 0
        buy1, buy2 = sys.maxsize, sys.maxsize
        sell1, sell2 = 0, 0

        for price in prices:
            buy1 = min(price, buy1)
            sell1 = max(sell1, price - buy1)
            buy2 = min(buy2,price - sell1)
            sell2 = max(sell2, price - buy2)
        return sell2
```

## Complexity

- time: O(n)
- space: O(1)
