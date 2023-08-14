# Majority Element
We can use Moore's Voting Algorithm to solve the problem. We can take the first item of the list and set it to cur. We can create a counter for this item. If the next item is different we subtract one, otherwise we add one. When the counter gets down to zero we assign current element to the next one. The last element standing is the majority element
```python3
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        cur = nums[0]
        cnt = 1
        for i in range(len(nums)):
            if nums[i] == cur:
                cnt += 1
            else:
                cnt -= 1
            if cnt <=0:
                cur = nums[i]
                cnt = 1
        return cur
```
# Proof Of Moore's Voting Algorithm
If the element is the majority element, it will be possible to cancel out all other elements. Eventually the majority of one lement will take over. It's easy to see if we sort the items in the array.
