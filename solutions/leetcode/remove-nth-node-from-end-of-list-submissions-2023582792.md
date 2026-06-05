# remove nth node from end of list/submissions/2023582792

**Platform:** LeetCode  
**Date:** 2026-06-05  

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
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode* fast = head;
        ListNode* slow = head;
        for(int i=1;i<=n;i++){
            fast=fast->next;
        }
        if(fast==NULL){
            return head->next;
        }
        while(fast->next!=NULL){
            slow=slow->next;
            fast=fast->next;
        }
        slow->next  = slow->next->next;
        return head;
    }
};
```
