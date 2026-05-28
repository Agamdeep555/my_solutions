# jump game ii/submissions/2015773263

**Platform:** LeetCode  
**Date:** 2026-05-28  

## Solution

```
class Solution {
public:
    int jump(vector<int>& nums) {
        int l = 0;
        int r = 0;
        int jump  = 0;
        for(int i=0;i<nums.size()-1;i++){
            int l = i+1;
            int r = i+nums[i];
            jump++;
            if(r>=nums.size()-1) return jump;
        }
        return jump;

    }
};
```
