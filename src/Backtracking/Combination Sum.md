# Combination Sum

Problem page:[https://leetcode.com/problems/combination-sum](https://leetcode.com/problems/combination-sum)

## Solution

```python
class Solution:
    def combinationSum(self, candidates: List[int], target: int) -> List[List[int]]:
        res = []
        def helper(index,strs,total):
            if total == target:
                res.append(strs[:])
                return
            if total > target or index >= len(candidates):
                return
            strs.append(candidates[index])
            helper(index,strs,total + candidates[index])
            strs.pop()
            helper(index+1,strs,total)
            return res
        return helper(0,[],0)
```

## Complexity

- time: O(2^n)
- space: O(n)
