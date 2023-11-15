# Permutations In String
```python
class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
        left = 0
        right = 0
        cur_sum = 3**ord(s2[0])
        target_sum = 0
        for i in s1:
            target_sum += 3**ord(i)
        while right < len(s2):
            if right - left < len(s1) - 1:
                if right < len(s2) - 1:
                    right += 1
                    cur_sum += 3**ord(s2[right])
                else:
                    return False
            else:
                if cur_sum == target_sum:
                    return True
                else:
                    if right < len(s2) - 1:
                        cur_sum -= 3**ord(s2[left])
                        left += 1
                        right += 1
                        cur_sum += 3**ord(s2[right])
                    else:
                        return False
        return False
```
