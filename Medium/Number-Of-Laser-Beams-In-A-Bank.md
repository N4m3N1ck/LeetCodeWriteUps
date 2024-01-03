# Number Of Laser Beams in a bank
We will create a variable prev_row, which will store the previous row with lasers. For each row, if it has lasers, we will multiply it with the previous row, and set the current row to the previous row. All the products will be added together.
```python
class Solution:
    def numberOfBeams(self, bank: List[str]) -> int:
        ans = 0
        prev_row = 0
        for i in bank:
            count = i.count("1")
            if count > 0:
                ans += prev_row * count
                prev_row = count
        return ans
```
