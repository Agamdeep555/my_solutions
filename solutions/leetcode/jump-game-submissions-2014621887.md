# jump game/submissions/2014621887

**Platform:** LeetCode  
**Date:** 2026-05-27  

## Solution

```
class Solution {
public:
    bool canJump(vector<int>& nums) {
        int lastpos = nums.size()-1;
        for(int i=nums.size()-2;i>=0;i--){
            if(i+nums[i]>=lastpos){
                lastpos = i;
            }
        }
        return lastpos==0;
    }
};
```
