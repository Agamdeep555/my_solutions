# number of substrings containing all three characters/submissions/2020445118

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    int numberOfSubstrings(string s) {
        int left = 0;
        int ans = 0;
        unordered_map<char,int> mpp;

        for(int r=0;r<s.size();r++){
            mpp[s[r]]++;

            while(mpp['a']>0 && mpp['b']>0 && mpp['c']>0){
                mpp[s[left]]--;
                left++;
            }
            ans += left;
        }
        return ans;
    }
};
```
