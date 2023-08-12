# Balanced Binary Tree
We can solve this problem by calculating the height difference between each root.left and root.right. If at least one of the height differences is more than one the tree is unbalanced. If all of the differences are less than two, the tree is balanced.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def heightDifference(self,root):
        if root == None:
            return [0,True]
        l = self.heightDifference(root.left)
        r = self.heightDifference(root.right)
        
        return [max(l[0],r[0])+1,abs(l[0]-r[0])<=1 and l[1] and r[1]]
    def isBalanced(self, root: Optional[TreeNode]) -> bool:
        return self.heightDifference(root)[1]
```
