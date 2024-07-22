# Valid Parentheses

Problem page:[https://leetcode.com/problems/valid-parentheses](https://leetcode.com/problems/valid-parentheses)

## Solution

```python
def isValid(self, s: str) -> bool:
        stack = []
        matching = {")":"(", "}":"{", "]":"["}
        for char in s:
            if char in matching.values():
                stack.append(char)
            elif char in matching.keys():
                if not stack or matching[char] != stack.pop():
                    return False
        return not stack
```

## Complexity

- time: O(n)
- space: O(n)
