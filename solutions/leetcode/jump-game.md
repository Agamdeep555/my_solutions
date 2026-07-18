# jump game

**Platform:** LeetCode  
**Date:** 2026-07-18  

## Solution

```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int last = nums.size();
        for(int i=nums.size()-2;i>=0;i--){
            if(i+1+nums[i]>=last){
                last = i;
            }
        }
        if(last==0) return true;
        else return false;
    }
};
```
