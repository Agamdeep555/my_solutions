# combination sum ii/submissions

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    void func(int i, vector<int>& candidates,int target , set<vector<int>>& ans, vector<int> arr){
        if(i>=candidates.size()){
        if(target==0){
            ans.insert(arr);
        }
        return;
        }
        if(target < 0)
            return;

        arr.push_back(candidates[i]);
        func(i+1,candidates,target-candidates[i],ans,arr);

        arr.pop_back();
        func(i+1,candidates,target,ans, arr);
    }
    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {
        set<vector<int>> ans;
        vector<int> arr;
        sort(candidates.begin(),candidates.end());
        func(0,candidates,target,ans,arr);

        return vector<vector<int>>(ans.begin(),ans.end());
    }
};
```
