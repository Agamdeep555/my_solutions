# vertical order traversal of a binary tree/submissions

**Platform:** LeetCode  
**Date:** 2026-06-29  

## Solution

```
class Solution {
public:
    map<int, vector<pair<int,int>>> mpp;

    void func(TreeNode* root, int row, int col) {
        if(root == NULL) return;

        mpp[col].push_back({row, root->val});

        func(root->left, row + 1, col - 1);
        func(root->right, row + 1, col + 1);
    }

    vector<vector<int>> verticalTraversal(TreeNode* root) {
        func(root, 0, 0);

        vector<vector<int>> ans;

        for(auto &it : mpp) {
            auto vec = it.second;

            sort(vec.begin(), vec.end());

            vector<int> temp;

            for(auto &p : vec) {
                temp.push_back(p.second);
            }

            ans.push_back(temp);
        }

        return ans;
    }
};
```
