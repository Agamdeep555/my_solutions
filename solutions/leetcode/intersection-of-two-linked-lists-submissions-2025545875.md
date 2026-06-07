# intersection of two linked lists/submissions/2025545875

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
    ListNode *getIntersectionNode(ListNode *headA, ListNode *headB) {
        ListNode* temp1 = headA;
        ListNode* temp2 = headB;

        int cnt1 = 0;
        int cnt2=0;
        while(temp1!=NULL){
            temp1=temp1->next;
            cnt1++;
        }
        while(temp2!=NULL){
            temp2=temp2->next;
            cnt2++;
        }

        while(cnt1>cnt2){
            headA=headA->next;
            cnt1--;
        }
        while(cnt1<cnt2){
            headB=headB->next;
            cnt2--;
        }
        while(headA!=NULL){
            if(headA==headB){
                return headA;
            }
            headA=headA->next;
            headB=headB->next;
        }
        return NULL;
    }
};
```
