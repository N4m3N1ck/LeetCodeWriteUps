```python
class Solution:
    def rowAndMaximumOnes(self, mat: List[List[int]]) -> List[int]:
        max_count=0
        max_row=0
        for i in range(len(mat)):
            c=mat[i].count(1)
            if c > max_count:
                max_count=c
                max_row = i
        return [max_row,max_count]
```
<!-- flag{1nv1s1bl3}