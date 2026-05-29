# length of last word

**Platform:** LeetCode  
**Date:** 2026-05-29  

## Solution

```
class Solution {
public:
    int lengthOfLastWord(string s) {

        int count = 0;
        int j = s.size()-1;
        int k = 0;
        while(k<s.size()){
            if(j >= 0 && s[j] == ' '){
                j--;
            }
            else{
                break;
            }
            k++;
        }


        while(j >= 0 && s[j]!=' '){
            j--;
            count++;
        }
        return count;
    }
};
```
