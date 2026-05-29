# length of last word/submissions/2016463093

**Platform:** LeetCode  
**Date:** 2026-05-29  

## Solution

```
class Solution {
public:
    int lengthOfLastWord(string s) {

        int count = 0;
        int j = s.size()-1;

        while(j >= 0 && s[j]==' '){
            j--;
        }


        while(j >= 0 && s[j]!=' '){
            j--;
            count++;
        }
        return count;
    }
};
```
