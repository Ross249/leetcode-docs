# Simplify Path

Problem page:[https://leetcode.com/problems/simplify-path](https://leetcode.com/problems/simplify-path)

## Solution

```python
def simplifyPath(self, path: str) -> str:
        stack = []
        array = path.split('/')
        for dir in array:
            if dir == '.' or not dir:
                continue
            elif dir == '..':
                if stack:
                    stack.pop()
            else:
                stack.append(dir)
        return '/' + '/'.join(stack)
```

## Complexity

- time: O(n)
- space: O(n)
