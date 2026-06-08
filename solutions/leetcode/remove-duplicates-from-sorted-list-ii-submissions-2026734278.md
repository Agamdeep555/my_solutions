# remove duplicates from sorted list ii/submissions/2026734278

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
    ListNode* deleteDuplicates(ListNode* head) {
        if(head == NULL) return NULL;

        
        vector<int> arr;

        ListNode* temp = head;
        while (temp != NULL) {
            arr.push_back(temp->val);
            temp = temp->next;
        }

        vector<int> ans;
        int i = 0;
        while(i<arr.size()){
            int j = i + 1;
            if (j < arr.size() && arr[i] == arr[j]) {
                while (j < arr.size() && arr[i] == arr[j]) {
                    j++;
                }
                i = j;
            } else {
                ans.push_back(arr[i]);
                i++;
            }
        }
        if(ans.empty()) return NULL;
        ListNode* newnode = new ListNode(ans[0]);
        ListNode* phead = newnode;
        ListNode* start = newnode;
        for(int i=1;i<ans.size();i++){
            ListNode* newnode = new ListNode(ans[i]);
            phead ->next = newnode;
            phead = newnode;

        }
        return start;
    }
};
```
