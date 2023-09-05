# Binary Tree Preorder Traversal
# Recursive
The Solution is very similar to inorder traversal problem, but we firstly append the current root to the answer, and only after that we continue to the left, and after we finished left, we go to the right.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        ans = []
        def traversal(root):
            if not root:
                return
            ans.append(root.val)
            traversal(root.left)
            traversal(root.right)
        traversal(root)
        return ans
```
# Iterative
The iterative solution to this problem is extremely simple. All we do is create a stack [root], pop the top element on each iteration and push right first and left second, so that the left node will be proccessed first with its children.
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def preorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        if root == None:
            return None
        ans = []
        stack = [root]
        while stack:
            cur = stack.pop()
            if cur.right: 
                stack.append(cur.right)
            if cur.left:
                stack.append(cur.left)
            ans.append(cur.val)
        return ans
```
