# Maximum Depth Of Binary Tree
We can solve the problem recursively. The base case will be if root is None and we will return 0, because if root is None there is no tree. Otherwise we will return the maximum value between depths of the children + 1 (because root is not none)
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if root == None:
            return 0
        return max(self.maxDepth(root.left),self.maxDepth(root.right))+1
```
