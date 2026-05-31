# valid palindrome/submissions/2018461850

**Platform:** LeetCode  
**Date:** 2026-05-31  

## Solution

```
class Solution {
public:
    bool isPalindrome(string s) {
        int i = 0;
        int j = s.size();
        while(i<j){
            while(i<j && !isalnum(s[i])) i++;
            while(i<j && !isalnum(s[j])) j--;

            if(tolower(s[i]) != tolower(s[j])){
                return false;
            }
            i++;
            j--;
        }
        return true;
    }
};
```
