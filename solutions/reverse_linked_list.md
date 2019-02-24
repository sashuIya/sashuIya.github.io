```py
# Definition for singly-linked list.
class ListNode(object):
  def __init__(self, x):
    self.val = x
    self.next = None
```

# Рекурсивная версия:
```py
def reverseListRecursively(self, prev, current):
  head = current
  if current.next != None:
    head = self.reverseListRecursively(current, current.next)
  current.next = prev
  return head

def reverseList(self, head):
  """
  :type head: ListNode
  :rtype: ListNode (head of the reversed list)
  """
  if head == None: return None

  return self.reverseListRecursively(None, head)
```

## Замечания:
1. Время: `O(n)` (проходимся по всему списку один раз); доп. память: `O(n)` (аргументы рекурсивной функции складываются в стэк).
2. Решение очень концептуальное. Стоит его понимать.
