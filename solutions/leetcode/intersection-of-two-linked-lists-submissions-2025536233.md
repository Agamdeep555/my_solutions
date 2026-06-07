# intersection of two linked lists/submissions/2025536233

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
    ListNode* getIntersectionNode(ListNode* headA, ListNode* headB) {
        
        while (headA != NULL) {
            ListNode* temp = headB;
            while (temp != NULL) {

                if (headA == temp) {
                    return headA;
                }

                temp = temp->next;
            }
            headA = headA->next;
        }
        return NULL;
    }
};
```
