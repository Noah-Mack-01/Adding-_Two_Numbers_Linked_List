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
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        return addTwoNodesHelper(l1, l2, 0);
    }
    
    // we can solve this through recursion pretty easily
    private ListNode addTwoNodesHelper(ListNode l1, ListNode l2, int remainder) {
        
        // handles if l2 is null or if both are null
        if (l2 == null) {
            return addSingleValue(l1, remainder);
        }
        
        //handles if l1 is null
        else if (l1 == null) { 
            return addSingleValue(l2, remainder);
        }
        
        else {
            
            int one = l1.val;
            int two = l2.val;
            
            int newRem = (one + two + remainder) / 10;
            int newRes = (one + two + remainder) % 10;
            
            ListNode next = addTwoNodesHelper(l1.next, l2.next, newRem);
            ListNode res = new ListNode(newRes, next);
            return res;
        }
        
        
    }
    
    //adds a single integer value to a node, carrying it through the whole amount.
    private ListNode addSingleValue(ListNode l1, int i) {
        
        if (i <= 0) { 
            return l1;
        }
        
        if (l1 == null) {
            return new ListNode(i);
        }
        
        else {
            int newVal = (l1.val + i) % 10;
            int newRem = (l1.val + i) / 10;
            ListNode next = addSingleValue(l1.next, newRem);
            ListNode res = new ListNode(newVal, next);
            return res;
        }
    }
    
    
}
