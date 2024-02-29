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
            return None
        queue = [root]
        last = root
        while queue:
            cur = queue.pop(0)
            last = cur
            if cur.right:
                queue.append(cur.right)
            if cur.left:
                queue.append(cur.left)
        return last.val
```
