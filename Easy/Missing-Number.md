# Missing Number
Let's see what the array would look like if no numbers where missing. Let's choose n=5 and the missing number is 3. We will get [0,1,2,x,4,5]. The array contains n+1 elements and the first element of the array is 0, while the last element is n. We can calculate the sum using this formula: n*(T<sub>0</sub>+T<sub>n</sub>)/2. n is the length of the array, T<sub>0</sub> is the first element of the array, and T<sub>n</sub> is the last element of the array. We can change this formula for our problem and we get (n+1)*(0+n)/2. We can subtract the actual sum of the array and we will find the missing number
```python
class Solution:
    def missingNumber(self, nums: List[int]) -> int:
        return (len(nums)*(len(nums)+1))//2 - sum(nums)
```
