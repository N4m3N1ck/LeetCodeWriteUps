# Find Bottom Left Tree Value
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def findBottomLeftValue(self, root: Optional[TreeNode]) -> int:
        if root == None:
            return
        queue = [(root, 0)]
        current_row = []
        current_depth = 0
        while queue:
            cur = queue.pop(0)
            if cur[1] > current_depth:
                current_row = []
                current_depth += 1
            current_row.append(cur)
            if cur[0].left:
                queue.append((cur[0].left,cur[1] + 1))
            if cur[0].right:
                queue.append((cur[0].right, cur[1] + 1))
        return current_row[0][0].val
```
