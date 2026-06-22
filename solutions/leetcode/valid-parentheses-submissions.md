# valid parentheses/submissions

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class Solution {
public:
    bool isValid(string s) {
        stack<int> s;
        for(int i=0;i<s.size();i++){
            if(s[i]=='(' || s[i]=='[' || s[i]=='{'){
                s.push(s[i]);
            }
            else{
                
            }
        }
    }
};
```
