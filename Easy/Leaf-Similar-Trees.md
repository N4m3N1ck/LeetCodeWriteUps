# Leaf Similar Trees
Create a helper function leaves, which will get all the leaves from left to right (classic dfs). Compare the two outputs to get the answer
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def leafSimilar(self, root1: Optional[TreeNode], root2: Optional[TreeNode]) -> bool:
        def leaves(root):
            if root == None:
                return [None]
            answer = []
            stack = [root]
            while stack:
                cur = stack.pop()
                if not cur.left and not cur.right:
                    answer.append(cur.val)
                if cur.left:
                    stack.append(cur.left)
                if cur.right:
                    stack.append(cur.right)
            return answer
        return leaves(root1) == leaves(root2)
```
