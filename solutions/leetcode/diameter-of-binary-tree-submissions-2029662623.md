# diameter of binary tree/submissions/2029662623

**Platform:** LeetCode  
**Date:** 2026-06-11  

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
    int diameter = 0;

    int func(TreeNode* root){
        
        if(root==NULL) return 0;

        int left = func(root->left);
        int right = func(root->right);


        diameter = max(diameter,left+right);
        return  1+max(left,right);
    }
    int diameterOfBinaryTree(TreeNode* root) {
        func(root);
        return diameter;

    }
};
```
