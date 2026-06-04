# reverse linked list/submissions/2022267618

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        ListNode* curr = head;
        ListNode* prev = NULL;
        ListNode* forw = head;

        while(curr!=NULL){
            forw = forw->next;
            curr->next = prev;
            prev = curr;
            curr = forw;
            
        }
        return prev;
    }
};
```
