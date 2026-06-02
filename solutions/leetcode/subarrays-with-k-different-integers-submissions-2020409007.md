# subarrays with k different integers/submissions/2020409007

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
    int atmost(vector<int>& fruits,int k) {
        unordered_map<int, int> mpp;
        int total = 0;
        int left = 0;

        for (int r = 0; r < fruits.size(); r++) {

            mpp[fruits[r]]++;

            while (mpp.size() > k) {
                mpp[fruits[left]]--;
                if (mpp[fruits[left]] == 0) {
                    mpp.erase(fruits[left]); 
                }
                left++;
            }
            total += (r - left + 1);

        }
        return total;
    }
public:
    int subarraysWithKDistinct(vector<int>& nums, int k) {
            return atmost(nums,k)-atmost(nums,k-1);
    }
};
```
