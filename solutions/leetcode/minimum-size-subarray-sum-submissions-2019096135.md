# minimum size subarray sum/submissions/2019096135

**Platform:** LeetCode  
**Date:** 2026-06-01  

## Solution

```
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        sort(nums.begin(),nums.end());
        int mini = INT_MAX;
        for(int l = 0; l<nums.size()-1;l++){
            int r = l;
            while(r<nums.size()){
                int sum;
                if(l==r) sum = nums[l];
                else sum = nums[l]+nums[r];
                if(sum==target){
                    int val = r-l+1;
                    mini = min(mini,val);
                    break;
                }
                else if(sum>target){
                    break;
                }
                else{
                    r++;
                }
            }
        }
        if(mini!=INT_MAX){
            return mini;
        }
        return 0;
    }
};
```
