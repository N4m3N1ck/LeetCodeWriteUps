# Diameter Of Binary Tree
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def diameterOfBinaryTree(self, root: Optional[TreeNode]) -> int:
        def helper(root):
            if root == None:
                return (-1,0)
            left = helper(root.left)
            right = helper(root.right)
            height = max(left[0], right[0]) + 1
            diameter = max(left[1],right[1],left[0] + right[0] + 2)
            return (height, diameter)
            
            
        return helper(root)[1]
```
