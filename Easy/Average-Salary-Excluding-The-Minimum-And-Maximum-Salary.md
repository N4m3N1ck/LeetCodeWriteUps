# Average Salary Excluding The Minimum And Maximum Salary
# Approach 1 - one-liner
```python
class Solution:
    def average(self, salary: List[int]) -> float:
        return (sum(salary) - max(salary) - min(salary))/(len(salary) - 2)
```
# Approach 2 - one pass
```python
class Solution:
    def average(self, salary: List[int]) -> float:
        mi = salary[0]
        ma = salary[0]
        s = 0
        l = -2
        for i in salary:
            if i < mi:
                mi = i
            if i > ma:
                ma = i
            s += i
            l += 1
        return (s - mi - ma) / l
```
