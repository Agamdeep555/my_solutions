# product of array except self/submissions/2016181215

**Platform:** LeetCode  
**Date:** 2026-05-29  

## Solution

```
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n = nums.size();
        vector<int> pre(n);
        vector<int> post(n);
        vector<int> ans(n);
        pre[0] =1;
        int premul = 1;
        for(int i=1;i<nums.size();i++){
            pre[i] = nums[i-1]*premul;
            premul = pre[i];
        }

        int postmul = 1;
        post[nums.size()-1] = 1;
        for(int i=nums.size()-2;i>=0;i--){
            post[i]= nums[i+1]*postmul;
            postmul = post[i];
        }
        for(int i=0;i<nums.size();i++){
            ans[i] = pre[i]*post[i];
        }
        return ans;
    }
};
```
