#Two Sum
  An obvious solution would be to just loop through each item in the array (i) and than loop through each item after i to find j so that target = i+j. Complexity of the algorithm is O(n^2) which is too slow.
##The correct solution would be this:
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        num_dict = {}
        for i in range(len(nums)):
            j = target - nums[i]
            if j in num_dict:
                return [i,num_dict[j]]
            num_dict[nums[i]] = i
```
##Explanation
  Firstly we create an empty dictionary in which we are going to store each number and it's index. When we meet a number which is complemetary to one of the previous nubmers stored in the dictionary we will return the number and the index of the complimentary number
