# generate parentheses/submissions/2037895195

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    void func(int i, int open, vector<string> &ans, string str){
        if(i==0){
            while(open>0){
                str = str + ')';
                open--;
            }
            ans.push_back(str);
            return;
        }
        // take
        func(i-1,open+1,ans,str+'(');
        // not take
         if(open > 0) {
            func(i, open - 1, ans, str + ')');
        }
    }
    vector<string> generateParenthesis(int n) {
        vector<string> ans;
        func(n-1,1,ans,"(");
        return ans;
    }
};
```
