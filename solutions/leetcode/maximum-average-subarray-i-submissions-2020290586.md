# maximum average subarray i/submissions/2020290586

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    double findMaxAverage(vector<int>& nums, int k) {
        
        double sum;
        for(int i=0;i<k;i++){
            sum += nums[i];
        }
        double maxi = sum/k;

        int left  = 0;
        double avg;
        for(int r = 1;r<= nums.size()-k;r++){

            sum = sum - nums[left] + nums[r+k-1];
            avg = sum/k;
            left++;

            if(maxi<avg){
                maxi = avg;
            }
            

        }
        return maxi;
    }
};
```
