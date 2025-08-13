# Binary Tree Level Order Traversal

## Problem Description

Given the `root` of a binary tree, return _the level order traversal of its
nodes ' values_. (i.e., from left to right, level by level).



**Example 1:**

![](https://assets.leetcode.com/uploads/2021/02/19/tree1.jpg)

    
    
    **Input:** root = [3,9,20,null,null,15,7]
    **Output:** [[3],[9,20],[15,7]]
    

**Example 2:**

    
    
    **Input:** root = [1]
    **Output:** [[1]]
    

**Example 3:**

    
    
    **Input:** root = []
    **Output:** []
    



**Constraints:**

  * The number of nodes in the tree is in the range `[0, 2000]`.
  * `-1000 <= Node.val <= 1000`



## Your Submission

```python3
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        ans = []
        if root is None:
            return ans


        q = deque()
        q.append(root)

        while q:
            size = len(q)
            lvl = []

            for i in range(size):
                node = q.popleft()
                lvl.append(node.val)

                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)

            ans.append(lvl)

        return ans

        
```
