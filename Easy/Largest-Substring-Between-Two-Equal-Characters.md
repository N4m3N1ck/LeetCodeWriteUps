# Largest Substring Between Two Equal Characters
We will store the first and the last occurance of the character in a dictionary.
```python
class Solution:
    def maxLengthBetweenEqualCharacters(self, s: str) -> int:
        dic = {}
        max_dist = -1
        for i in range(len(s)):
            if s[i] not in dic:
                dic[s[i]] = [i,i]
            else:
                dic[s[i]][1] = i
                if i - dic[s[i]][0] - 1 > max_dist:
                    max_dist = i - dic[s[i]][0] - 1
        return max_dist
```
