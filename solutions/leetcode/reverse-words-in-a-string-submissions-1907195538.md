# reverse words in a string/submissions/1907195538

**Platform:** LeetCode  
**Date:** 2026-05-30  

## Solution

```
class Solution {
public:
    string reverseWords(string s) {
        int i = s.size()-1;
        string ans;

        while(i>=0){
            string str;
            if(s[i]!=' '){
                str = str + s[i];
                if(s[i-1]==' ' && i-1>=0){
                    
                }
            }
            ans = ans + str + ' ';
            i--;
        }
        return ans;
    }
};
```
