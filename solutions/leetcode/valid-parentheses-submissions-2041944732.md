# valid parentheses/submissions/2041944732

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class Solution {
public:
    bool isValid(string s) {
        stack<int> st;
        for(int i=0;i<s.size();i++){
            if(s[i]=='(' || s[i]=='[' || s[i]=='{'){
                st.push(s[i]);
            }
            else{
                if(s[i]==')' && !st.empty() && st.top()=='('){
                    st.pop();
                }
                else if(s[i]==']' && !st.empty()    && st.top()=='['){
                    st.pop();
                }
                else if(s[i]=='}' && !st.empty() && st.top()=='{'){
                    st.pop();
                }
                else{
                    return false;
                }

            }
        }
        if(st.empty()) return true;
        else return false;
    }
};
```
