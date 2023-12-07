# Calculate Money In Leetcode Bank
During the first week he will earn 1 + 2 +3 + 4 + 5 + 6 + 7 or 28 dollars. Each next week he will start with one more dollar and will earn 7 more dollars that week. There will be 1 + 2 + 3 ... + n extra sevens. We can calculate the amount of sevens using the formula n * (n + 1) / 2.
```python
class Solution:
    def totalMoney(self, n: int) -> int:
        week_count = n // 7
        return week_count * (n % 7) + (n % 7) * (n % 7 + 1) // 2 + 7 * (week_count - 1) * week_count // 2 + 28 * week_count
```
