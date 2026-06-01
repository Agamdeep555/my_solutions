# Intuition

**Platform:** LeetCode  
**Date:** 2026-06-01  

## Solution

```
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int mini = INT_MAX;
        int left = 0;
        int sum = 0;
        for(int i=0;i<nums.size();i++){
            sum = sum + nums[i];

            while(sum>=target){
                mini = min(mini,i-left+1);
                sum -= nums[left];
                left++;
            }
        }
        return mini == INT_MAX ? 0 : mini;
    }
};
```
