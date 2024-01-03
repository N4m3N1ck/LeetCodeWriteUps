# Number Of Laser Beams in a bank
For each row, add the product of this row with the previous row with lasers.
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
