# Valid Parentheses
  This is a very popular algorithm problem which you must know how to solve. Solution involves data structure known as stack
## Solution
```python
class Solution:
    def isValid(self, s: str) -> bool:
        pairs = {
            ")": "(",
            "]": "[",
            "}": "{"
        }
        stack = []
        for i in s:
            if i in "([{":
                stack.append(i)
            elif len(stack)>0:
                if stack[-1] == pairs[i]:
                    stack.pop()
                else:
                    return False
            else:
                return False
        return len(stack)==0
```
  We will store a dictionary of parentheses pairs to reduce the amount of if conditions we make. We will loop through each item in string s and add it to the stack if it is an opening parenthese. If it is the closing parenthese we will check if the previous one corresponds to it and remove it from the stack. If it isn't of the same type, we will return False. We will also return False if there are too many closing parentheses or the stack is not empty in the end
