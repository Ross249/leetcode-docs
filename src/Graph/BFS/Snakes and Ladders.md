# Snakes and Ladders

Problem page:[https://leetcode.com/problems/snakes-and-ladders](https://leetcode.com/problems/snakes-and-ladders)

## Solution

```python
class Solution:
    def snakesAndLadders(self, board: List[List[int]]) -> int:
        n = len(board)
        def helper(label):
            r, c = divmod(label-1, n)
            if r % 2 == 0:
                return n - 1 - r, c
            else:
                return n - 1 - r, n - 1 - c
        tmp = set()
        queue = deque()
        queue.append((1,0))
        while queue:
            label, step = queue.popleft()
            r, c = helper(label)
            if board[r][c] != -1:
                label = board[r][c]
            if label == n ** 2:
                return step
            for x in range(1, 7):
                n_label = label + x
                if n_label <= n ** 2 and n_label not in tmp:
                    tmp.add(n_label)
                    queue.append((n_label,step + 1))
        return -1
```

## Complexity

- time: O(n\*n)
- space: O(n\*n)
