```python
class Solution:
    def maxScore(self, s: str) -> int:
        zero_count = 0
        ones_count = s.count("1")
        max_score = 0
        for i in range(len(s)-1):
            if s[i] == "0":
                zero_count += 1
            elif s[i] == "1":
                ones_count -= 1
            if zero_count + ones_count > max_score:
                max_score = zero_count + ones_count
        return max_score
```
