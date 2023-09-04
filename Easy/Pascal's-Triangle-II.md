# Pascal's Triangle II
We can create two arrays: prev and cur. We will add 0 to the front and to the back of the prev array. We will create two pointers - l and r. We will add the sum of those pointers to the cur array and make prev array equal to cur array. cur array will be set to []. We will return prev array after the loop is finished.
```python
class Solution:
    def getRow(self, rowIndex: int) -> List[int]:
        prev = [1]
        cur = []
        for i in range(rowIndex):
            prev = [0]+prev+[0]
            l = 0
            r = 1
            while r < len(prev):
                cur.append(prev[l]+prev[r])
                l += 1
                r += 1
            prev = cur
            cur = []
        return prev
```
