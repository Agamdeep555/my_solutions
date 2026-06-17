# subsets ii/submissions

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    void func(int idx, vector<int>& nums, set<vector<vector<int>>> &ans , vector<int> arr){
        if(idx==nums.size()){
            ans.push_back(arr);
            return;
        }

        arr.push_back(nums[idx]);
        func(idx+1,nums,ans,arr);

        arr.pop_back();
        func(idx+1,nums,ans,arr);
    }
    vector<vector<int>> subsetsWithDup(vector<int>& nums) {
        set<vector<vector<int>>> ans;
        vector<int> arr;

        func(0,nums,ans,arr);
        return ans;
    }
};
```
