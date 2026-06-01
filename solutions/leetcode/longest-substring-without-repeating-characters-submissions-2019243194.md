# longest substring without repeating characters/submissions/2019243194

**Platform:** LeetCode  
**Date:** 2026-06-01  

## Solution

```
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
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
