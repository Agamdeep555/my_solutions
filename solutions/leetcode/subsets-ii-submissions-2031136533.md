# subsets ii/submissions/2031136533

**Platform:** LeetCode  
**Date:** 2026-06-12  

## Solution

```
class Solution {
    private:
    void func(int idx ,int n, vector<int>& nums,vector<int> &ds, vector<vector<int>> &ans ){
        if(idx==n){
            ans.push_back(ds);
            return;
        }
        ds.push_back(nums[idx]);
        func(idx+1,n,nums,ds,ans);
        ds.pop_back();

        while(idx+1<n && nums[idx]==nums[idx+1]){
            idx++;
        }

        func(idx+1,n,nums,ds,ans);
    }
public:
    vector<vector<int>> subsetsWithDup(vector<int>& nums) {
        vector<vector<int>> ans;
        vector<int> ds;
        sort(nums.begin(), nums.end()); 
        func(0,nums.size(),nums,ds,ans);
        return ans;
    }
};
```
