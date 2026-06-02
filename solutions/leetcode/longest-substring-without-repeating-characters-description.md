# longest substring without repeating characters/description

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        if(s.size()==0) return 0;
        unordered_map<char,int> mpp;
        int left = 0;
        int maxi = INT_MIN;

        for(int r = 0;r<s.size();r++){
            mpp[s[r]]++;

            while(mpp[s[r]]>1){
                mpp[s[left]]--;
                left++;
            }
            maxi = max(maxi,r-left+1);
        }
        return maxi;
    }
};
```
