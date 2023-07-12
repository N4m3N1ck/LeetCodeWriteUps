# Longest Common Prefix
There are multiple ways to approach the problem
## Solution 1: while satisfies condition
```python
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        last_prefix=""
        while True:
            for i in strs:
                if i[:len(last_prefix)] != last_prefix:
                    return last_prefix[:-1]
            if len(last_prefix) < len(strs[0]):
                last_prefix+=strs[0][len(last_prefix)]
            else: 
                return last_prefix
```
We can add one letter from the first word in the list to the prefix while all other words have this prefix. When we run out of letters we return the first word. We keep going while the prefix doesn't satisfy the condition and return last correct prefix
## Solution 2: import os
```python
import os
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str: 
        return os.path.commonprefix(strs)
```
## Solution 3: lexicographic sort
```python
import os
class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str: 
        strs.sort()
        a = strs[0]
        b = strs[-1]
        prefix = b
        other = a
        if len(a)<len(b):
            prefix = a
            other = b
        while other[:len(prefix)] != prefix:
            prefix = prefix[:-1]
        return prefix
```
We can find two words that have the most different prefix by sorting the array lexicographically. We can then pick the shortest of them and make it the prefix and reduce it while it isn't the prefix of the other word.
