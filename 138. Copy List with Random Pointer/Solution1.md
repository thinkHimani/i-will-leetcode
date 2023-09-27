Question: https://leetcode.com/problems/copy-list-with-random-pointer/description/
```python
"""
# Definition for a Node.
class Node:
    def __init__(self, x: int, next: 'Node' = None, random: 'Node' = None):
        self.val = int(x)
        self.next = next
        self.random = random
"""

class Solution:
    def copyRandomList(self, head: 'Optional[Node]') -> 'Optional[Node]':
        mmap = {None:None}

        curr = head
        while curr:
            copy = Node(curr.val)
            mmap[curr] = copy
            curr = curr.next

        curr = head
        while curr:
            copy = mmap[curr]
            copy.next = mmap[curr.next]
            copy.random = mmap[curr.random]
            curr = curr.next

        return mmap[head]


```
