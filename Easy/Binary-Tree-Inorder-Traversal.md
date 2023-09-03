# Binary Tree Inorder Traversal
# Recursive Approach
We can make a function that will go to the left as deep as possible, then it will add root, and then it will go to the right as far as possible
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def inorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        ans = []
        def traversal(root):
            if root == None:
                return
            traversal(root.left)
            ans.append(root.val)
            traversal(root.right)
        traversal(root)
        return ans
```
