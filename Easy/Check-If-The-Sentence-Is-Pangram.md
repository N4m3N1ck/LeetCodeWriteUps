# Check If The Sentence Is Pangram
# Soltuion 1: check each letter
```python
class Solution:
    def checkIfPangram(self, sentence: str) -> bool:
        if len(sentence)<26:
            return False
        for i in "abcdefghijklmnopqrstuvwxyz":
            if i not in sentence:
                return False
        return True
```
# Solution 2: set
```python
class Solution:
    def checkIfPangram(self, sentence: str) -> bool:
        return len(set(sentence))==26
```
