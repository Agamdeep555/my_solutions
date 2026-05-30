# reverse words in a string

**Platform:** LeetCode  
**Date:** 2026-05-30  

## Solution

```
class Solution {
public:
    string reverseWords(string s) {
        int i = s.size() - 1;
        string ans;

        while (i >= 0) {
            string str;
            
            if (s[i] != ' ') {
                int j = i;

                while (j >= 0 && s[j] != ' ') {
                    str = str + s[j];
                    j--;
                }
                reverse(str.begin(),str.end());
                ans = ans + str + ' ';
                i = j;
            }
            else{
                i--;
            }
        }
        if (!ans.empty())
            ans.pop_back();

        return ans;
    }
};
```
