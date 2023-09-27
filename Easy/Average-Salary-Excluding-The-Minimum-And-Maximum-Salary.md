# Average Salary Excluding The Minimum And Maximum Salary
# Approach 1 - one-liner
```python
class Solution:
    def average(self, salary: List[int]) -> float:
        return (sum(salary) - max(salary) - min(salary))/(len(salary) - 2)
```
