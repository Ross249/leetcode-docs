# Best Time to Buy and Sell Stock IV

Problem page:[https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iv](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-iv)

## Solution

```python
class Solution:
    def maxProfit(self, k: int, prices: List[int]) -> int:
        if k == 0: return 0
        dp=[[1000,0]for _ in range(k + 1)]
        for price in prices:
            for i in range(1, k + 1):
                dp[i][0] = min(dp[i][0],price - dp[i - 1][1])
                dp[i][1] = max(dp[i][1], price - dp[i][0])
        return dp[k][1]
```

## Complexity

- time: O(n \* k)
- space: O(k)
