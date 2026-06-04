# merge two sorted lists/submissions/2022312958

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
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {

        ListNode* head1 = list1;
        ListNode* head2 = list2;

        if (head1 == NULL)
            return head2;
        if (head2 == NULL)
            return head1;

        ListNode* temp = NULL;

        if (head1->val <= head2->val) {
            temp = head1;
            head1 = head1->next;
        } else {
            temp = head2;
            head2 = head2->next;
        }
        ListNode* ans = NULL;
        ans = temp;
        while (head1 != NULL && head2 != NULL) {
            if (head1->val <= head2->val) {

                ans->next = head1;
                head1 = head1->next;
            } else {

                ans->next = head2;
                head2 = head2->next;
            }
            ans = ans->next;
        }
        while (head1 != NULL) {
            ans->next = head1;
            head1 = head1->next;
            ans = ans->next;
        }

        while (head2 != NULL) {
            ans->next = head2;
            head2 = head2->next;
            ans = ans->next;
        }
        return temp;
    }
};
```
