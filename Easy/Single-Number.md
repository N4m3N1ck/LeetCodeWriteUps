# Single number
There are multiple ways to solve the problem.
# Dictionary
We can store the amount of times we meet each number in the dictionary and then check for the number that was found only once.
```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        dic = {}
        for i in nums:
            if i not in dic:
                dic[i] = 1
            else:
                dic[i]+=1
        for i in dic:
            if dic[i]==1:
                return i
```
# Set
If we show the sum of all the elements in the array as **sum+x**, where x is our target, if we convert the array to set, the sum will be **sum/2 + x**, so **2\*(sum/2+x) = sum + 2x**. If we subtract **sum+x** from **sum+2x** we will solve x.
```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        return 2*sum(set(nums))-sum(nums)
```
# XOR
