# jump game/submissions/2015746585

**Platform:** LeetCode  
**Date:** 2026-05-28  

## Solution

```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int maxi=0;
        for(int i=0;i<nums.size()-1;i++){
            maxi = max(maxi,i+nums[i]);
            if(maxi>=nums.size()-1) break;
        }
        if(maxi>=nums.size()-1) return true;
        else return false;
    }
};
```
