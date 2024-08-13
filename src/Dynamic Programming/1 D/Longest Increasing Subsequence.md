# Longest Increasing Subsequence

Problem page:[https://leetcode.com/problems/longest-increasing-subsequence](https://leetcode.com/problems/longest-increasing-subsequence)

## Solution

```python
class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
	# DP solution is easy but slow
        # if not nums:
        #     return 0
        # n = len(nums)
        # dp = [1] * n
        # for i in range(1, n):
        #     for j in range(i):
        #         if nums[i] > nums[j]:
        #             dp[i] = max(dp[i], dp[j] + 1)
        # return max(dp)
        res = []
        def helper(res, n):
            left, right = 0, len(res) - 1
            while left <= right:
                mid = (left + right) // 2
                if res[mid] == n:
                    return mid
                elif res[mid] > n:
                    right = mid - 1
                else:
                    left = mid + 1
            return left
        for n in nums:
            if not res or res[-1] < n:
                res.append(n)
            else:
                index = helper(res,n)
                res[index] = n
        return len(res)
```

## Complexity

- time: O(n \* log n)
- space: O(n)
