# Binary Tree Level Order Traversal
We will use DFS to solve this problem. In cur, we will store the nodes of the current level, in to_add, we will store all the children in the nodes of the current level. The first level of a binary tree is the root node, so we will add it to the queue. We will pop nodes in the queue (which represents the current level) one by one, and add their children to the to_add list. After there are no nodes in the queue left( the level  is traversed), we will add the cur array to ans. We will add all the nodes from to_add array which represent the next level.
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
