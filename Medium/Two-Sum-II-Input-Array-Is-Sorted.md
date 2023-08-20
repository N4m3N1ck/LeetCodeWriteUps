# Two Sum II - Input Array Is Sorted
We can create two pointers: left and right. In each step we will check the sum of the pointers, if the sum is less than the target, we will increase the left pointer, if the sum is more than the target, we will reduce the right pointer
```python
class Solution:
    def twoSum(self, numbers: List[int], target: int) -> List[int]:
        l = 0
        r = len(numbers)-1
        while l<r:
            s = numbers[l]+numbers[r]
            if s == target:
                return [l+1,r+1]
            if s<target:
                l+=1
            else:
                r-=1
```
