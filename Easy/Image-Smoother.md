# Image Smoother
Create a matrix ans, try to get all of the cells in the matrix adjacent by one to the current cell, add the avg to ans matrix.
```python
class Solution:
    def imageSmoother(self, img: List[List[int]]) -> List[List[int]]:
        y = len(img)
        x = len(img[0])
        ans = []
        for i in range(y):
            ans.append([])
            for i in range(x):
                ans[-1].append(0)
        for i in range(len(img)):
            for j in range(len(img[i])):
                s = img[i][j]
                c = 1
                if i - 1 >= 0 and j - 1 >= 0:
                    s += img[i-1][j-1]
                    c += 1
                if i - 1 >= 0:
                    s += img[i-1][j]
                    c += 1
                if j - 1 >= 0:
                    s += img[i][j-1]
                    c += 1
                if i + 1 < y and j + 1 < x:
                    s += img[i+1][j+1]
                    c += 1
                if i + 1 < y:
                    s += img[i+1][j]
                    c += 1
                if i + 1 < y and j - 1 >= 0:
                    s += img[i+1][j-1]
                    c += 1
                if i - 1 >= 0 and j + 1 < x:
                    s += img[i-1][j+1]
                    c += 1
                if j + 1 < x:
                    s += img[i][j+1]
                    c += 1
                ans[i][j] = s // c
        return ans
```
