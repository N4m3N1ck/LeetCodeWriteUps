# Minimum Depth Of Binary Tree
There are multiple ways to approach the problem:
# Recursive
We can return 0 if there is no root, and then we can return min depth between two children if both of them exist, otherwiser return the depth of the single child.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def minDepth(self, root: Optional[TreeNode]) -> int:
        if root == None:
            return 0
        if root.left and root.right:
            return min(self.minDepth(root.left), self.minDepth(root.right))+1
        if root.left:
            return self.minDepth(root.left)+1
        return self.minDepth(root.right)+1
```
