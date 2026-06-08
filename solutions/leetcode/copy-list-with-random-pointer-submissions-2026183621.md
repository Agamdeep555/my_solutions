# copy list with random pointer/submissions/2026183621

**Platform:** LeetCode  
**Date:** 2026-06-08  

## Solution

```
class Solution {
public:
    Node* copyRandomList(Node* head) {
        if (!head) return NULL;

        unordered_map<Node*, Node*> mp;

        Node* temp = head;

        while (temp) {
            mp[temp] = new Node(temp->val);
            temp = temp->next;
        }

        temp = head;

        while (temp) {
            mp[temp]->next = mp[temp->next];
            mp[temp]->random = mp[temp->random];
            temp = temp->next;
        }

        return mp[head];
    }
};
```
