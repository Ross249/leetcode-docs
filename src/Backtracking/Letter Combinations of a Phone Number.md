# Letter Combinations of a Phone Number

Problem page:[https://leetcode.com/problems/letter-combinations-of-a-phone-number](https://leetcode.com/problems/letter-combinations-of-a-phone-number)

## Solution

```python
class Solution:
    def letterCombinations(self, digits: str) -> List[str]:
        if not digits:
            return []

        dictionary = {
            '2': 'abc',
            '3': 'def',
            '4': 'ghi',
            '5': 'jkl',
            '6': 'mno',
            '7': 'pqrs',
            '8': 'tuv',
            '9': 'wxyz',
        }
        res = []
        def helper(index,strs):
            if index == len(digits):
                res.append(strs[:])
                return
            for letter in dictionary[digits[index]]:
                helper(index + 1, strs + letter)
        helper(0,"")
        return res
```

## Complexity

- time: O(4^n \* n)
- space: O(4^n \* n)
