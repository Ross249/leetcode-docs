# LRU Cache

Problem page:[https://leetcode.com/problems/lru-cache](https://leetcode.com/problems/lru-cache)

## Solution

```python
class LRUCache:
    _flag = ('data','capacity')

    def __init__(self, capacity: int):
        self.data: Dict[int,int] = OrderedDict()
        self.capacity = capacity

    def get(self, key: int) -> int:
        return -1 if key not in self.data else self.data.setdefault(key, self.data.pop(key))

    def put(self, key: int, value: int) -> None:
        try:
            self.data.move_to_end(key)
            self.data[key] = value
        except KeyError:
            self.data[key] = value
            if len(self.data) > self.capacity:
                self.data.popitem(last=False)
```

## Complexity

- time: O(1)
- space: O(n)
