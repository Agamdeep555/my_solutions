# find the index of the first occurrence in a string/description

**Platform:** LeetCode  
**Date:** 2026-05-31  

## Solution

```
class Solution {
public:
    int strStr(string haystack, string needle) {
        int i = 0;
        while(i<haystack.size()){
            int m = 0;
            if(haystack[i]==needle[m]){
                int k = 0;
                int j = i;
                while(k<needle.size() && j < haystack.size()){
                    if(haystack[j]==needle[k]){
                        j++;
                        k++;
                    }
                    else{
                        break;
                    }
                    if(k==needle.size()) return i;
                }
            }
            i++;
        }
        return -1;
    }
};
```
