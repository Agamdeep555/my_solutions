# Intuition

**Platform:** LeetCode  
**Date:** 2026-05-29  

## Solution

```
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        string s = strs[0];

        int kmin = INT_MAX;


        for(int i=1;i<strs.size();i++){
            string c = strs[i];
            int k =0;

            while(k<s.size() && k<c.size() && s[k]==c[k]){
                k++;
            }
            
            kmin = min(kmin,k);
        }
        string ans="";
         for(int i = 0; i < kmin; i++) {
            ans += s[i];
        }

        return ans;
        
    }
};
```
