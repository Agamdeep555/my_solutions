# add two numbers/submissions/2023594621

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
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode* ans = new ListNode();
        int cnt = l1->val + l2->val;
        l1 = l1->next;
        l2 = l2->next;

        int l;
        int u=0;
        if(cnt>9){
            u = 1;
            l = cnt % 10;
            ans->val = l;
        }
        else{
            ans->val = cnt;
        }
        ListNode* final = ans;
        ListNode* temp1 = l1;
        ListNode* temp2 = l2;

        while(temp1!=NULL || temp2!=NULL || u){
            int sum = u;

            if(temp1!=NULL){
                sum += temp1->val;
                temp1= temp1->next;
            }
            if(temp2!=NULL){
                sum += temp2->val;
                temp2 = temp2->next;
            }
            u = sum/10;
            ans->next = new ListNode(sum % 10);
            ans = ans->next;
        }
        return final;
        
    }
};
```
