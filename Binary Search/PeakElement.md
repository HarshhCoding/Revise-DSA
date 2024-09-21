# 162. Find Peak Element

## [Problem Link ](https://leetcode.com/problems/find-peak-element/description/)

```
Example 1:

Input: nums = [1,2,3,1]
Output: 2
Explanation: 3 is a peak element and your function should return the index number 2.
Example 2:

Input: nums = [1,2,1,3,5,6,4]
Output: 5
Explanation: Your function can return either index number 1 where the peak element is 2, or index number 5 where the peak element is 6.
```



## Approach

1. apply binary search 


## Solution 



```java
     public int findPeakElement(int[] nums) {
        
        int n = nums.length;
        int l = 0;
        int r = n-1;
    
        while (l != r ){
           int mid = (l+r)/2;
            if(nums[mid] < nums[mid+1])
                l = mid+1;
            else
                r= mid;
            }
        return l;
    }
    
```
### Time Complexity : `O(log n)`


### Space Complexity : `O(1)`