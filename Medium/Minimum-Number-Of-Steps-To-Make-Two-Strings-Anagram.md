# Minimum Number of Steps to Make Two Strings Anagram
What we can do is find how many extra characters of each letter there are in s compared to t. If we take s = "leetcode" and t = "practise" these are the extra characters in s: {'e': 2, 'l': 1, 'o': 1, 'd': 1}. It will be equal to the amount of extra characters in t, so if we replace each of these extra characters with the extra characters in t, we will get anagrams.
```python
class Solution:
    def minSteps(self, s: str, t: str) -> int:
        c1 = Counter(s)
        c2 = Counter(t)
        ans = c1 - c2
        x = 0
        for i in ans:
            x += ans[i]
        return x
```
