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
  def searchBSTRecursive(self, node, val):
    if node is None:
      return None
    
    if node.val == val:
      return node
    elif val < node.val: # value is in the left part - go left
      return self.searchBSTRecursive(node.left, val)
    else: # val > node.val; value is in the right part - go right
      return self.searchBSTRecursive(node.right, val)


  def searchBST(self, root, val):
    """
    :type root: TreeNode
    :type val: int
    :rtype: TreeNode
    """
    return self.searchBSTRecursive(root, val)
```

## Замечания:
`h` - высота дерева (максимум - `n`)
Время: `O(h)`
Память: `O(h)`
