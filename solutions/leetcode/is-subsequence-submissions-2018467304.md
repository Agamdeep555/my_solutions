# is subsequence/submissions/2018467304

**Platform:** LeetCode  
**Date:** 2026-05-31  

## Solution

```
class Solution {
public:
    bool isSubsequence(string s, string t) {
        if(s.empty()) return true;
        int j = 0;
        int i = 0;

        while(i<s.size() && j<t.size()){
            if(s[i]==t[j]){
                i++;
                j++;
            }
            else{
                j++;
            }
            if(i==s.size()) return true;
        }
        return false;
    }
};
```
