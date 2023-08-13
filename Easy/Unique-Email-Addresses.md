# Unique Email Addresses
We can loop through each email, split it into two parts: before @ and after @. We will remove all the characters from left part that come after plus. We will remove all "." characters as well. We will check if the new email already exists
```python
class Solution:
    def numUniqueEmails(self, emails: List[str]) -> int:
        decoded = []
        n = 0
        for i in emails:
            left,right = i.split("@")
            left = left.split("+")[0]
            while "." in left:
                left = left.replace(".","")
            new = left+"@"+right
            if new not in decoded:
                decoded.append(new)
                n+=1
        return n
```
