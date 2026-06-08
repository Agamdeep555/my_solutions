# copy list with random pointer/submissions/2026180516

**Platform:** LeetCode  
**Date:** 2026-06-08  

## Solution

```
/*
// Definition for a Node.
class Node {
public:
    int val;
    Node* next;
    Node* random;
    
    Node(int _val) {
        val = _val;
        next = NULL;
        random = NULL;
    }
};
*/

class Solution {
public:
    Node* copyRandomList(Node* head) {
        if(head==NULL) return NULL;
        Node* temp = head;
        unordered_map<Node*, Node*> mp;
        
        int x = temp->val;

        Node* startnode = new Node(x);
        Node* ans = startnode;

        Node* phead = startnode;
        mp[temp] = startnode;

        temp = temp->next;

        while(temp!=NULL){
            int x = temp->val;
           Node* newnode = new Node(x);
           phead->next = newnode;
           phead = newnode;

           mp[temp] = newnode;
           temp = temp -> next;


        }

        phead = ans;
        Node* temp2 = head;
        while(temp2!=NULL){
            phead->random = mp[temp2->random];
            temp2 = temp2->next;
            phead = phead->next;
        }
        return ans;
    }
};
```
