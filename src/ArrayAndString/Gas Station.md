# Gas Station

Problem page:[https://leetcode.com/problems/gas-station](https://leetcode.com/problems/gas-station)

## Solution

```python
class Solution:
    def canCompleteCircuit(self, gas: List[int], cost: List[int]) -> int:
        s_cost, s_gas = sum(cost), sum(gas)
        if s_cost > s_gas:
            return -1
        c_gas, idx = 0, 0
        for i in range(len(gas)):
            c_gas += gas[i] - cost[i]
            if c_gas < 0:
                c_gas = 0
                idx = i + 1
        return idx
```

## Complexity

- time: O(n)
- space: O(1)
