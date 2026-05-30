# find the index of the first occurrence in a string/submissions/2017556975

**Platform:** LeetCode  
**Date:** 2026-05-30  

## Solution

```
class Solution {
public:
    int strStr(string haystack, string needle) {
        int i = 0;
        while(i<haystack.size()){
            if(haystack[i]==needle[i]){
                int k = 0;
                int j = i;
                while(k<needle.size()){
                    if(haystack[j]==needle[j]){
                        j++;
                    }
                    else{
                        break;
                    }
                    k++;
                    if(k==needle.size()) return i;
                }
            }
            i++;
        }
        return -1;
    }
};
```
