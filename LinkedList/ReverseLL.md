# 206. Reverse Linked List

## [Problem Link ](https://leetcode.com/problems/reverse-linked-list/description/)

```
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]

Input: head = []
Output: []
```



## Approach

1. recursive approach
![alt text](Images/recursive%20reverse%20ll.png)

2. Iterative approach
![alt text](Images/iterative%20approach%20rev%20ll.png)



## Solution 

1. Recursive approach

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
    public ListNode reverseList(ListNode head) {
       
        if(head == null || head.next == null) return head;
        ListNode p = reverseList (head.next);
        head.next.next = head;
        head.next = null;
        return p;
    }
}
    
```
### Time Complexity : `O(n)`


### Space Complexity : `O(n)`
##
2. Iterative approach

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
    public ListNode reverseList(ListNode head) {
        ListNode prev = null;
        ListNode curr = head;

        while(curr != null){
            ListNode next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;

        }
        return prev;
    }
}
    
```
### Time Complexity : `O(n)`


### Space Complexity : `O(1)`