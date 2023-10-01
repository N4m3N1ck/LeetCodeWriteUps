```python
class Solution:
    def buyChoco(self, prices: List[int], money: int) -> int:
        min_1 = 101
        min_2 = 101
        for i in prices:
            if i < min_1:
                min_2 = min_1
                min_1 = i
            elif i < min_2:
                min_2 = i
        if min_1 + min_2 <= money:
            return money - min_1 - min_2
        return money
```