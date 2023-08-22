# Daily Temperatures
We can solve this problem using stack. We will go though each element in the array and if it is larger than any of the previous elements in the stack, we will remove them from the stack and at the item's index we will store the distance between the current and the item. After that we will append current item to the stack. This way we will remove all the previous items that havent found the larger item correctly.
```python
class Solution:
    def dailyTemperatures(self, temperatures: List[int]) -> List[int]:
        stack = []
        ans = [0]*len(temperatures)
        for i in range(len(temperatures)):
            while stack and temperatures[stack[-1]] < temperatures[i]:
                ans[stack[-1]] = i - stack[-1]
                stack.pop()
            stack.append(i)
        return ans
```
