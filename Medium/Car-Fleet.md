# Car Fleet
```python
class Solution:
    def carFleet(self, target: int, position: List[int], speed: List[int]) -> int:
        ar = []
        for i in range(len(position)):
            ar.append((position[i], speed[i]))
        ar.sort(key = lambda x: x[0])
        stack = []
        for i in ar:
            stack.append(i)
        ans = 1
        fleet_lead = stack.pop()
        fleet_lead_time = (target - fleet_lead[0]) / fleet_lead[1]
        while len(stack) > 0:
            time = (target - stack[-1][0]) / stack[-1][1]
            if time <= fleet_lead_time:
                stack.pop()
            else:
                ans += 1
                fleet_lead = stack.pop()
                fleet_lead_time = (target - fleet_lead[0]) / fleet_lead[1]
        return ans
```
