# Maximum SUM of subarray of length K

[Problem Link ](https://www.geeksforgeeks.org/problems/max-sum-subarray-of-size-k5313/1)


## Solution 



```c++
long maximumSumSubarray(int K, vector<int> &Arr , int N){
        long sum = 0;
        long max;
        for (int i = 0; i<K; i++){
            sum += Arr[i];
        }
        max = sum;
        for (int i = 1; i<=N - K; i++){
            sum = sum - Arr[i-1] + Arr[i+K-1];
            max = std::max(max, sum);
        }
        return max;
    }
```
### Time Complexity : `O(n)`


### Space Complexity : `O(1)`