# jump game/submissions/2014610454

**Platform:** LeetCode  
**Date:** 2026-05-27  

## Solution

```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int i=0;
        int x =0;
        while(x<nums.size()){
            x = x + nums[i];
            if(x==i) return false;
            i=x;
            if(x==nums.size()-1){
            return true;
            }
        }
        return false;

    }
};
```
