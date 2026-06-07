# rotate list/submissions/2025716162

**Platform:** LeetCode  
**Date:** 2026-06-07  

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

        while(k--){


            ListNode* temp = head;

            while(temp->next->next != NULL) {
            temp = temp->next;
            }
            int val = temp->next->val;
            delete temp->next;
            temp->next = NULL;

            ListNode* newNode = new ListNode(val);

            newNode->next = head;
            head = newNode;
        }
        return head;
    }
};
```
