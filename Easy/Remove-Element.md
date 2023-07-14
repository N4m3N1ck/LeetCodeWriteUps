# Remove Element
The solution is going to be very similar to the problem Remove Duplicates From Sorted Array. We will replace the first elements of the list with the ones that are not equal to val
For example: [3,2,2,3], val = 3
1. 3 is equal to 3 so we ignore it
2. 2 is not equal to three, so we replace the first element with 2: [2,2,2,3]
3. 2 is not equal to three, so we replace the second element with 2: [2,2,2,3]
4. 3 is equal to three, so we ignore it
5. We get array [2,2,2,3] in which only the first to elements matter
```python
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        cur = 0
        for i in nums:
            if i != val:
                nums[cur]=i
                cur+=1
        return cur
```
