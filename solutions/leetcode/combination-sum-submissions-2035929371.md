# combination sum/submissions/2035929371

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    void func(int idx, vector<int>& candidates, int target, set<vector<int>> &ans, int sum, vector<int> &arr){


        if (idx == candidates.size()) {
            if(target == sum){
                ans.insert(arr);
            }
            return;
        }
        if(sum>target) return;

        arr.push_back(candidates[idx]);
        func(idx,candidates,target,ans,sum+candidates[idx],arr);

        arr.pop_back();
        func(idx+1,candidates,target,ans,sum,arr);

    }
    vector<vector<int>> combinationSum(vector<int>& candidates, int target) {

        set<vector<int>> ans;
        vector<int> arr;
        func(0,candidates,target,ans,0,arr);
        return vector<vector<int>>(ans.begin(),ans.end());
    }
};
```
