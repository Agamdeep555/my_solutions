# jump game ii/submissions/2015785472

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
        
        while(r<nums.size()-1){
            int far = 0;
            for(int i=l;i<=r;i++){
                far = max(far,i+nums[i]);
            }
            l = r+1;
            r = far;
            jump++;
        }
        return jump;

    }
};
```
