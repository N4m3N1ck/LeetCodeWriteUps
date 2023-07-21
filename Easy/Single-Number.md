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
Wen can use an operation like XOR to calculate the target number. For example: we have an array [5,5,1]. 5^5 = 0; 0^1 = 1. 1 is the target
```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        val = 0
        for i in nums:
            val ^= i
        return val
```
We can improve the algorithm by using nums[0] instead of val:
```python
class Solution:
    def singleNumber(self, nums: List[int]) -> int:
        for i in range(1,len(nums)):
            nums[0] ^= nums[i]
        return nums[0]
```
