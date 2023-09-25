Question: https://leetcode.com/problems/merge-two-sorted-lists/
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode()
        mergeList = dummy

        while list1 and list2:
            if list1.val < list2.val:
                mergeList.next = list1
                list1 = list1.next
                mergeList = mergeList.next
            else:
                mergeList.next = list2
                list2 = list2.next
                mergeList = mergeList.next

        if not list1:
            while list2:
                mergeList.next = list2
                list2 = list2.next
                mergeList = mergeList.next
        else:
            while list1:
                mergeList.next = list1
                list1 = list1.next
                mergeList = mergeList.next
        
        return dummy.next
```
