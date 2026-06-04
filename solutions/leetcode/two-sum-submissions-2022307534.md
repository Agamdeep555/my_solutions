# two sum/submissions/2022307534

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
         int n = nums.size();
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                if(i!=j && nums[i]+nums[j]==target){
                   return {i,j};
                }

            }
        }
        return {};
    }
};
```
