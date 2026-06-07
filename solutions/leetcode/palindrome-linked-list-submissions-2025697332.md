# palindrome linked list/submissions/2025697332

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
    bool isPalindrome(ListNode* head) {
        if(head==NULL || head->next == NULL) return true;
        ListNode* slow= head;
        ListNode* fast = head;

        while(slow->next !=NULL && fast->next !=NULL && fast->next->next != NULL){
            slow = slow ->next ;
            fast = fast -> next -> next;


        }   
        ListNode* prev = NULL;

        slow = slow->next;
        ListNode* curr = slow;
        ListNode* forw = slow;

        while(curr!=NULL){
            forw = forw->next;
            curr->next = prev;
            prev = curr;
            curr = forw;
            
        }
        

        
            
            ListNode* temp = head;
            while(prev!=NULL){
                if(temp->val != prev->val){
                    return false;
                }
                prev = prev ->next;
                temp = temp ->next;
            }
        
        return true;
    }
};
```
