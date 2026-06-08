# reverse linked list ii/submissions/2026316831

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
    ListNode* reverseBetween(ListNode* head, int left, int right) {
        if(head==NULL || head->next == NULL) return head;

        ListNode* curr = head;
        ListNode* lasthead = NULL;
        int y = left;
        while(y-1 > 0){
            lasthead = curr;
            curr=curr->next;
            y--;
        }
        

        ListNode* prev = NULL;
        ListNode* forw = curr;

        ListNode* start = curr;

        int x = right-left;
        while(x>=0){
            forw = curr->next;
            curr -> next = prev;
            prev = curr;
            curr = forw;
            x--;
        }

        if(lasthead)
            lasthead->next = prev;
        else
            head = prev;

        start ->next = curr;
        return head;
        
    }
};
```
