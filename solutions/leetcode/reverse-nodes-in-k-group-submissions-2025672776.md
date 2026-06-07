# reverse nodes in k group/submissions/2025672776

**Platform:** LeetCode  
**Date:** 2026-06-07  

## Solution

```
class Solution {
public:
    ListNode* reverse(ListNode* &head, int k, ListNode* prev) {
        ListNode* curr = head;
        ListNode* forw = NULL;

        while (k--) {
            forw = curr->next;
            curr->next = prev;
            prev = curr;
            curr = forw;
        }

        head = curr;
        return prev;
    }

    ListNode* reverseKGroup(ListNode* head, int k) {
        int cnt = 0;
        ListNode* temp = head;

        while (temp) {
            cnt++;
            temp = temp->next;
        }

        if (k == 1 || cnt < k) return head;

        ListNode* curr = head;

        ListNode* newHead = reverse(curr, k, NULL);
        ListNode* prevTail = head;   // old head becomes tail

        cnt -= k;

        while (cnt >= k) {
            ListNode* groupTail = curr;   // save start of current group

            ListNode* nextHead = reverse(curr, k, NULL);

            prevTail->next = nextHead;

            prevTail = groupTail;   // after reversal, start becomes tail

            cnt -= k;
        }

        prevTail->next = curr;

        return newHead;
    }
};
```
