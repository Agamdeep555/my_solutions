# rotate list/submissions/2026142556

**Platform:** LeetCode  
**Date:** 2026-06-08  

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
    ListNode* rotateRight(ListNode* head, int k) {

        if(head == NULL || head->next == NULL || k == 0)
            return head;
        
        ListNode* temp = head;
        int cnt = 0;
        while(temp!=NULL){
            temp=temp->next;
            cnt++;
        }
        k = k % cnt;

        int x = cnt - k -1;

        ListNode* temp2 = head;
        ListNode* curr = head;
        while(temp2->next!=NULL){
            temp2=temp2->next;
        }
        temp2->next = head;

        while(x--){
            curr=curr->next;
        }
        head = curr->next;
        curr->next = NULL;
        return head;
    }
};
```
