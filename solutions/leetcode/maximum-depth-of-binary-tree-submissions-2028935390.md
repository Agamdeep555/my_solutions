# maximum depth of binary tree/submissions/2028935390

**Platform:** LeetCode  
**Date:** 2026-06-10  

## Solution

```
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */
class Solution {
public:
    void func(TreeNode* &root, int cnt, int &ans){
        if(root==NULL) return;

        ans = max(ans,cnt);
        if(root->left){
            func(root->left,cnt+1, ans);
        }
        if(root->right){
            func(root->right,cnt+1,ans);
        }
    }
    int maxDepth(TreeNode* root) {
        if(root==NULL) return NULL;

        int cnt=1;
        int ans = 0;
        func(root,cnt,ans);
        return ans;
    }
};
```
