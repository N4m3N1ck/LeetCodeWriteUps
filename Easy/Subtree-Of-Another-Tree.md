# Subtree Of Another Tree
We can solve the problem by going through each node of the tree and checking if it is the same as the subTree. We can use the fucntion sameTree from the previous problems, and we can call this function for each element of the tree.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def sameTree(self,root,root2):
            if root == None and root2 == None:
                return True
            if root == None or root2 == None:
                return False
            return root.val == root2.val and self.sameTree(root.left,root2.left) and self.sameTree(root.right,root2.right)
    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        if subRoot==None:
            return True
        if root == None:
            return False
        if self.sameTree(root,subRoot):
            return True
        return self.isSubtree(root.left,subRoot) or self.isSubtree(root.right,subRoot)

```
