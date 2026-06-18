# combination sum ii/submissions/2037931214

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    void func(int i,
              vector<int>& candidates,
              int target,
              vector<vector<int>>& ans,
              vector<int>& arr) {

        if(target == 0){
            ans.push_back(arr);
            return;
        }

        if(i >= candidates.size() || target < 0)
            return;

        // take
        arr.push_back(candidates[i]);
        func(i+1, candidates, target-candidates[i], ans, arr);
        arr.pop_back();

        // skip duplicates in not-take branch
        int j = i + 1;
        while(j < candidates.size() &&
              candidates[j] == candidates[i]) {
            j++;
        }

        func(j, candidates, target, ans, arr);
    }

    vector<vector<int>> combinationSum2(vector<int>& candidates, int target) {

        sort(candidates.begin(), candidates.end());

        vector<vector<int>> ans;
        vector<int> arr;

        func(0, candidates, target, ans, arr);

        return ans;
    }
};
```
