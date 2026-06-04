# remove nth node from end of list/submissions/2022339736

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
    ListNode* removeNthFromEnd(ListNode* head, int n) {

        if(head == NULL) return NULL;
        if(head->next == NULL && n == 1) return NULL;

        ListNode* temp = head;
        int cnt=0;
        while(temp!=NULL){
            cnt++;
            temp=temp->next;
        }
        if(cnt == n) return head->next;

        int x = cnt-n-1;
        ListNode* temp2 = head;
        ListNode* ans = temp2;
        while(x>0){
            temp2=temp2->next;
            x--;
        }
        if(temp2->next->next != NULL){
            temp2->next = temp2->next->next;
        }
        else{
            temp2->next = NULL;
        }
        return ans;

    }

};
```
