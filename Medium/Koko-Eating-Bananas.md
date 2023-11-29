# Koko Eating Bananas
```python
class Solution:
    def minEatingSpeed(self, piles: List[int], h: int) -> int:
        def hours_to_eat(piles, k):
            count = 0
            for i in piles:
                if i <= k:
                    count += 1
                elif i % k == 0:
                    count += i // k
                else:
                    count += i // k + 1
            return count
        left = 1
        right = max(piles)
        while left < right:
            m = (left + right) // 2
            if h < hours_to_eat(piles, m):
                left = m + 1
            else:
                right = m
        return left
```
