# Path Sum
We can solve this problem recursively. We can return false if root is None and we can return true if value of root is equal to target and root has no children. Otherwise we will return hasPathSum(root.left) **or** hasPathSum(root.right)
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def hasPathSum(self, root: Optional[TreeNode], targetSum: int) -> bool:
        if root == None:
            return False
        if root.val == targetSum and root.left==None and root.right==None:
            return True
        return self.hasPathSum(root.left,targetSum-root.val) or self.hasPathSum(root.right,targetSum-root.val)
```
