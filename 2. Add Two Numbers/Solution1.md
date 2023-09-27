Question: https://leetcode.com/problems/add-two-numbers/
```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        sum_list_head = None
        sum_list_tail = None
        carry = 0
        digit_sum = 0
        
        while l1 and l2:
            digit_sum = l1.val + l2.val + carry
            if digit_sum >=10:
                carry =1
                digit_sum -= 10
            else: 
                carry = 0
            if not sum_list_head:
                sum_list_head = ListNode(digit_sum)
                sum_list_tail = sum_list_head
            else:
                sum_list_tail.next = ListNode(digit_sum)
                sum_list_tail = sum_list_tail.next
            l1 = l1.next
            l2 = l2.next
                
        while l1:
            digit_sum = l1.val + carry
            if digit_sum >=10:
                carry =1
                digit_sum -= 10
            else: 
                carry = 0
            if not sum_list_head:
                sum_list_head = ListNode(digit_sum)
                sum_list_tail = sum_list_head
            else:
                sum_list_tail.next = ListNode(digit_sum)
                sum_list_tail = sum_list_tail.next
            l1 = l1.next
                
        while l2:
            digit_sum = l2.val + carry
            if digit_sum >=10:
                carry =1
                digit_sum -= 10
            else: 
                carry = 0
            if not sum_list_head:
                sum_list_head = ListNode(digit_sum)
                sum_list_tail = sum_list_head
            else:
                sum_list_tail.next = ListNode(digit_sum)
                sum_list_tail = sum_list_tail.next
            l2 = l2.next
                
        if carry == 1:
            sum_list_tail.next = ListNode(1)
            sum_list_tail = sum_list_tail.next
            
        return sum_list_head

```
