```py
# Definition for singly-linked list.
# class ListNode(object):
#     def __init__(self, x):
#         self.val = x
#         self.next = None

def mergeTwoSortedLists(self, l1, l2):
  """
  :type l1: ListNode
  :type l2: ListNode
  :rtype: ListNode
  """
  if l1 == None: return l2
  if l2 == None: return l1

  if l2.val < l1.val:
    l1, l2 = l2, l1

  current_last = l1

  p1 = l1
  p2 = l2
  p1 = p1.next

  while p1 != None or p2 != None:
    if p1 == None:
      current_last.next = p2
      break
    if p2 == None:
      current_last.next = p1
      break

    if p2.val < p1.val:
      p1, p2 = p2, p1

    current_last.next = p1
    current_last = p1
    p1 = p1.next

  return l1
```

## Замечания:
1. `O(n)` по времени, `O(1)` по доп. памяти.
2. Этот алгоритм практически является итерацией merge sort'а.
