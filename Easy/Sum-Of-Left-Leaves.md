# Sum Of Left Leaves
If the current node is None or a leaf itself, then return 0. If the current node has a left leave, l = root.left.val. If current node doesnt have a left node, l = 0. If the current node has a left node, l = self.sumOfLeftLeaves(root.left). Assign r = self.sumOfLeftLeaves(root.right), return l + r
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def sumOfLeftLeaves(self, root: Optional[TreeNode]) -> int:
        if root == None or (root.left == None and root.right == None):
            return 0
        l = 0
        if root.left == None:
            l = 0
        elif root.left.left == None and root.left.right == None:
            l = root.left.val
        else:
            l = self.sumOfLeftLeaves(root.left)
        r = self.sumOfLeftLeaves(root.right)
        return l + r
```
