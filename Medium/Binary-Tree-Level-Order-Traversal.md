# Binary Tree Level Order Traversal
```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        if root == None:
            return
        queue = [root]
        ans = []
        cur = []
        to_add = []
        while queue:
            cur.append(queue[0].val)
            c = queue.pop(0)
            if c.left: to_add.append(c.left)
            if c.right: to_add.append(c.right)
            if len(queue) == 0:
                ans.append(cur)
                cur = []
                for i in to_add:
                    queue.append(i)
                to_add = []
        return ans
```
