# Letter Combinations Of A Phone Number
We will map all the letters to the corresponding numbers. Create an array ans to store all the combinations. Create a function backtrack() which accepts two parameters: c and s. c is the current digit index. s is the current string created. If the length of the string is complete, we will add it to the ans array. Otherwise we will loop through all the letters corresponding c digit and add them to the string in a new backtrack call
```python
class Solution:
    def letterCombinations(self, digits: str) -> List[str]:
        if not digits:
            return 
        dic = {"2":"abc","3":"def","4":"ghi","5":"jkl","6":"mno","7":"pqrs","8":"tuv","9":"wxyz"}
        ans = []
        def backtrack(c, s):
            if len(s) == len(digits):
                ans.append(s)
                return
            for i in dic[digits[c]]:
                backtrack(c + 1, s+i)
        backtrack(0, "")
        return ans
```
