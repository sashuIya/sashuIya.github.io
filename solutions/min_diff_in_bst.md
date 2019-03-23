```py
# Definition for a binary tree node.
class TreeNode(object):
  def __init__(self, x):
    self.val = x
    self.left = None
    self.right = None
```

```py
class Solution(object):
  def minDiffInBSTRecursive(self, node, prev_value, result):
    """
    :arg prev_value: A previous value if we had an array with sorted nodes' values.
                     E.g., if we have a BST of [-5, 4, 5, 7, 10, 12, 13, 17, 30, 100]
                     the previous for 10 is 7, the previous for 30 is 17.
    """
    if node is None:
      return
    
    # In-order traversal gives us a sorted order.
    # In-order traversal is
    #  1. go left
    #  2. check current node
    #  3. go right
    
    # 1. Go left
    self.minDiffInBSTRecursive(node.left, prev_value, result)

    # 2. Check the current node
    if prev_value[0] is not None:
      if result[0] is None:
        result[0] = node.val - prev_value[0]
      else:
        result[0] = min(result[0], node.val - prev_value[0])
    
    prev_value[0] = node.val
    
    # 3. Go right
    self.minDiffInBSTRecursive(node.right, prev_value, result)
    
  
  def minDiffInBST(self, root):
    """
    :type root: TreeNode
    :rtype: int
    """
    prev_value = [None]
    result = [None]
    self.minDiffInBSTRecursive(root, prev_value, result)
    
    return result[0]
```

## Замечания:
Память - O(n), время - O(n).
