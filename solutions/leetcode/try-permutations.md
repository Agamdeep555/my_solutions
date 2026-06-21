# Try  Permutations ||

**Platform:** LeetCode  
**Date:** 2026-06-21  

## Solution

```
class Solution {
public:
    void func(int i,vector<int>& nums, vector<int> &arr, vector<vector<int>>& ans, vector<int>& vis){
        if(i==nums.size()){
            ans.push_back(arr);
            return;
        }

        for(int j=0;j<nums.size();j++){
            if(vis[j]==0){
                arr.push_back(nums[j]);
                vis[j]=1;
                func(i+1,nums,arr,ans,vis);

                vis[j]=0;
                arr.pop_back();
            }
        }
    }
    vector<vector<int>> permute(vector<int>& nums) {

        vector<vector<int>> ans;
        vector<int> vis(nums.size(),0);
        vector<int> arr;
        func(0,nums,arr,ans,vis);
        return ans;
    }
};
```
