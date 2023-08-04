# Number Of Good Pairs
```python
class Solution:
    def numIdenticalPairs(self, nums: List[int]) -> int:
        c = 0
        v = []
        for i in nums:
            if i not in v:
                cnt = nums.count(i)
                c+= (cnt*(cnt-1))//2
                v.append(i)
        return c
```
We can notice a pattern in the amount of pairs depending on the count of an item. For example: An array [1,1,1,1] will have 3+2+1 pairs which is 6. Here is the formula where n is the count of an element: (n-1)*n/2. We can check if we already visited the item by storing it in a visited array.
