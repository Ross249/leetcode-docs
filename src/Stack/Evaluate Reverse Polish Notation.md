# Evaluate Reverse Polish Notation

Problem page:[https://leetcode.com/problems/evaluate-reverse-polish-notation](https://leetcode.com/problems/evaluate-reverse-polish-notation)

## Solution

```python
def evalRPN(self, tokens: List[str]) -> int:
        res = []
        for c in tokens:
            if c == "+":
                res.append(int(res.pop()) + int(res.pop()))
            elif c == "-":
                second, first = res.pop(), res.pop()
                res.append(first - second)
            elif c == "*":
                res.append(int(res.pop()) * int(res.pop()))
            elif c == "/":
                second, first = res.pop(),res.pop()
                res.append(int(int(first) / int(second)))
            else:
                res.append(int(c))
        return res[0]
```

## Complexity

- time: O(n)
- space: O(n)
