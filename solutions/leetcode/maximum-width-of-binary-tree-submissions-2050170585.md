# maximum width of binary tree/submissions/2050170585

**Platform:** LeetCode  
**Date:** 2026-06-29  

## Solution

```
class Solution {
public:
    long long ans = 0;
    vector<long long> first;

    void dfs(TreeNode* root, int level, long long idx) {
        if(root == NULL)
            return;

        if(level == first.size())
            first.push_back(idx);

        ans = max(ans, idx - first[level] + 1);

        long long cur = idx - first[level];
        dfs(root->left, level+1, 2*cur+1);
        dfs(root->right, level+1, 2*cur+2);
    }

    int widthOfBinaryTree(TreeNode* root) {
        dfs(root, 0, 0);
        return ans;
    }
};
```
