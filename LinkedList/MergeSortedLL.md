# 21. Merge Two Sorted Lists


## [Problem Link ](https://leetcode.com/problems/merge-two-sorted-lists/description/)

```
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]
Example 2:

Input: list1 = [], list2 = []
Output: []
Example 3:

Input: list1 = [], list2 = [0]
Output: [0]
```



## Approach

### 1. find which node has lesser value and join accordingly 


## Solution 


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
        ListNode prevNode = new ListNode(-1);
        ListNode prev = prevNode;

        while (list1 != null && list2 != null){
            if(list1.val <= list2.val){
                prev.next = list1;
                prev = list1;
                list1 = list1.next;
                
            }
            else {
                prev.next = list2;
                prev = list2;
                list2 = list2.next;
               
            }
        }
        if(list1 != null){
            prev.next = list1;
        }
        if(list2 != null){
            prev.next = list2;
        }
        return prevNode.next;
    }
}
    
```
### Time Complexity : `O(n)`


### Space Complexity : `O(1)`
