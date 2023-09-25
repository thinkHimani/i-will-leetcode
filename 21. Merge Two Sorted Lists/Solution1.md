Question: https://leetcode.com/problems/merge-two-sorted-lists/
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        // initializing
        ListNode newList = null, head = null;
        // initial conditions
        if(list1 != null && list2 != null && list1.val<= list2.val){
                newList = list1;
                head = newList;
                list1 = list1.next;
        }
        else if(list1 != null && list2 != null && list2.val<list1.val){
                newList = list2;
                head = newList;
                list2 = list2.next;
        }
        else{
            if(list1!=null && list2 == null){
                newList = list1;
                head = newList;
                list1 = list1.next;
            }
            if(list2!=null && list1 == null){
                newList = list2;
                head = newList;
                list2 = list2.next;
            }
        }
        // middle chunk
        while(list1 != null && list2 != null){
            if(list1 != null && list1.val<=list2.val){
                newList.next = list1;
                newList = newList.next;
                list1 = list1.next;
            }
            else if(list2 != null && list2.val<list1.val){
                newList.next = list2;
                newList = newList.next;
                list2 = list2.next;
            }
        }
        // end conditions if one of the list is empty or smaller
        if(list1==null){
            while(list2!=null){
                newList.next = list2;
                newList = newList.next;
                list2 = list2.next;
            }
        }
        else if(list2==null){
            while(list1!=null){
                newList.next = list1;
                newList = newList.next;
                list1 = list1.next;
            }
        }
        return head;
    }
}
```
