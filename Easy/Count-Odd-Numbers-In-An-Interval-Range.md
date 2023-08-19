# Count Odd Numbers In An Interval Range
There are (high+1)//2 odd numbers up to high, because if it's even we dont want to include high itself, but when it's odd we do. We dont add one to low because we want to exclude low itself from being subtracted.
```python
class Solution:
    def countOdds(self, low: int, high: int) -> int:
        return (high+1)//2 - low//2
```
