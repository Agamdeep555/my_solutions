# middle of the linked list/submissions/2022281847

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
    ListNode* middleNode(ListNode* head) {
        ListNode* slow = head;
        ListNode* fast = head;

        while(slow->next != NULL && fast->next!= NULL && fast->next->next!=NULL){
            slow = slow->next;
            fast = fast->next->next;

        }

        if(fast->next!=NULL){
            return slow->next;
        }
        else return slow;
    }
};
```
