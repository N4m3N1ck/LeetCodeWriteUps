# Replace Elements with Greatest Element on Right Side
I don't know why this one works:
```python
class Solution:
    def replaceElements(self, arr: List[int]) -> List[int]:
        if len(arr)==0:
            return []
        if len(arr) == 1:
            return [-1]
        dp = [-1] * len(arr)
        dp[-2] = arr[-1]

        for i in range(2,len(arr)):
            j = len(arr) - i - 1
            dp[j] = max(dp[j+2],dp[j+1],arr[j+1])
        return dp
```
# Final Solution
We can loop from the end of the array. For each element we can check if the next element is larget than the max value we already have. We can store the value of next element using last1 and last2
```python
class Solution:
    def replaceElements(self, arr: List[int]) -> List[int]:
        if len(arr) == 0:
            return []
        if len(arr) == 1:
            return [-1]
        last1 = arr[-2]
        last2 = -1
        arr[-2] = arr[-1]
        arr[-1] = -1
        i = len(arr)-3
        while i >= 0:
            last2 = last1
            last1 = arr[i]
            arr[i] = max(last2,arr[i+1])
            i-=1
        return arr
```
