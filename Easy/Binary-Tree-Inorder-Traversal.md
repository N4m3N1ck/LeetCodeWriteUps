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
# Iterative Approach
We can create an array ans and stack. We will set cur to root. While there are items in stack or cur, we will add the left of cur until we can't and after that we will pop current, add it to ans, and set it to right. If right is none we will just get back to the top item of the stack on the next iteration.
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
        stack = []
        cur = root
        while cur or stack:
            while cur:
                stack.append(cur)
                cur = cur.left
            cur = stack.pop()
            ans.append(cur.val)
            cur = cur.right
        return ans
```
