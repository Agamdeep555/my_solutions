# jump game/description

**Platform:** LeetCode  
**Date:** 2026-07-18  

## Solution

```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int last = nums.size()-1;
        for(int i=nums.size()-2;i>=0;i--){
            if(i+nums[i]>=last){
                last = i;
            }
            else{
                return false;
            }
        }
        return true;
    }
};
```
