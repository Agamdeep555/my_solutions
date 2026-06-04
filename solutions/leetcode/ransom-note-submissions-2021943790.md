# ransom note/submissions/2021943790

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    bool canConstruct(string ransomNote, string magazine) {
        unordered_map<char,int> mpp;

        for(char c: magazine){
            mpp[c]++;
        }
        for(int i=0;i<ransomNote.size();i++){
            if(mpp[ransomNote[i]]==0){
                return false;
            }
            mpp[ransomNote[i]]--;
        }
        return true;
    }
};
```
