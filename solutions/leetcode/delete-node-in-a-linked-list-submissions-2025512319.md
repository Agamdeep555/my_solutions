# delete node in a linked list/submissions/2025512319

**Platform:** LeetCode  
**Date:** 2026-06-07  

## Solution

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    void deleteNode(ListNode* node) {
        int val = node->val;
        int nextval = node->next->val;

        node->val = nextval;
        node->next->val = val;

        node->next = node->next->next;


    }
};
```
