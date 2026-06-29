# balanced binary tree/submissions/2050158481

**Platform:** LeetCode  
**Date:** 2026-06-29  

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
    int func(TreeNode* root){
        if(root == NULL){
            return 0;
        }
        int l = func(root->left);
        int r = func(root->right);

        return 1+max(l,r);
    }
    bool isBalanced(TreeNode* root) {

        if(root==NULL) return true;

        int l = func(root->left);
        int r = func(root->right);

        if(abs(l-r)>1) return false;

        bool left = isBalanced(root->left);
        bool right = isBalanced(root->right);

        if(!left || !right){
            return false;
        }
        return true;
    }
};
```
