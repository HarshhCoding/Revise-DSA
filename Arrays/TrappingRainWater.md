# Maximum SUM of subarray of length K

[Problem Link ](https://leetcode.com/problems/trapping-rain-water/solutions/5620351/beats-100-0ms-2-pointer-sol-with-explaination/)


## Solution 



```c++
int trap(vector<int>& height) {
        int water=0;
        int maxi = 0;
        int leftMaxHeight[height.size()];
        int rightMaxHeight[height.size()];

        for(int i=0; i<height.size(); i++){
            maxi = max(maxi, height[i]);
            leftMaxHeight[i]= maxi;
        }
        maxi= 0;
        for(int i=height.size()-1; i>=0; i--){
            maxi = max(maxi,height[i]);
            rightMaxHeight[i] = maxi;
        }

        for (int i = 1; i< height.size()-1; i++){

            water = water +min(leftMaxHeight[i], rightMaxHeight[i])- height[i];
        }
        return water;
    }

```
### Time Complexity : `O(n)`


### Space Complexity : `O(n)`