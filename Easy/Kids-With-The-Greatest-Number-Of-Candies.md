# Kids With The Greatest Number Of Candies
```python
class Solution:
    def kidsWithCandies(self, candies: List[int], extraCandies: int) -> List[bool]:
        m = max(candies)
        for i in range(len(candies)):
            candies[i] = candies[i]+extraCandies>=m
        return candies
``
