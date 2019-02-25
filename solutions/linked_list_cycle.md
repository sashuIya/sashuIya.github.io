```py
# Definition for singly-linked list.
class ListNode(object):
   def __init__(self, x):
       self.val = x
       self.next = None


def hasCycle(self, head):
  """
  :type head: ListNode
  :rtype: bool
  """
  if head == None: return False

  current = head
  steps = 1

  while True:
    next_node = current
    for step in range(steps):
      if next_node.next == None:
        return False

      next_node = next_node.next
      if next_node == current:
        return True

    current = next_node
    steps *= 2        
```

## Замечания:
1. Стоит понимать почему это решение за O(list.size()).
2. Это решение отлично от общеизвестного, что является вашим козырем.
