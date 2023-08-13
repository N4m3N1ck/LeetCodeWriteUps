# Product Of Array Except Self
We can calculate product before each element in the first loop. We can then calculate product after each element in the second loop. We can then multiply before and after array together.
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        before = [1]*len(nums)
        after = [1]*len(nums)
        for i in range(1,len(nums)):
            before[i] = before[i-1]*nums[i-1]
        for i in range(1,len(nums)):
            j = len(nums)-i-1
            after[j] = after[j+1] * nums[j+1]
        for i in range(len(before)):
            before[i]*=after[i] 
        return before
