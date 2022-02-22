## question

Given the head of a sorted linked list, delete all nodes that have duplicate numbers, leaving only distinct numbers from the original list. Return the linked list sorted as well.

Constraints:
The number of nodes in the list is in the range [0, 300].
-100 <= Node.val <= 100
The list is guaranteed to be sorted in ascending order.

```
Input: head = [1,1,1,2,3]
Output: [2,3]

Input: head = [1,2,3,3,4,4,5]
Output: [1,2,5]
```

### Thought process
INPUT: the head pointer of a link list

Solution1:
1. I think any single pointer list question can change this list into a double pointer list including a 'before' and a 'after'pointer.
2. When we find the duplicate target, we can follow the 'before' pointer and find the 'cut point'.

Solution2:
1. We can use map to identify the duplicate values and form a new List
2. It is easy to translate Python's list to a link list.

```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def deleteDuplicates(self, head: ListNode) -> ListNode:
        def createNewList():
            last = None
            head = None
            for val, count in M.items():
                if count != 1:
                    continue
                if not last:
                    last = head = ListNode(val, None)
                    continue
                node = ListNode(val, None)
                last.next = node
                last = node
            return head

        def debug(_pt):
            while _pt and _pt.val != None:
                print(_pt.val)
                _pt = _pt.next

        M = {}
        _pt = head
        while _pt and _pt.val != None:
            val = _pt.val
            if not M.get(val):
                M[val] = 1
            else:
                M[val] += 1
            _pt = _pt.next

        
        head = createNewList()
        return head
```

```
def listToNodeList(L):
    head = None
    last_node = None
    while len(L):
        val = L.pop(0)
        if not head:
            last_node = head = ListNode(val)
            continue
        else:
            new_node = ListNode(val)
            last_node.next = new_node
            last_node = new_node
    return head
```