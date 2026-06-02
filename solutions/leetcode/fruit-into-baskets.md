# fruit into baskets

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    int totalFruit(vector<int>& fruits) {
        if (fruits.size() == 2)
            return 2;
        if (fruits.size() == 1)
            return 1;
        if (fruits.size() == 0)
            return 0;

        unordered_map<int, int> mpp;
        int maxi = 0;
        int total = 0;
        int left = 0;

        for (int r = 0; r < fruits.size(); r++) {

            mpp[fruits[r]]++;
            total++;

            while (mpp.size() > 2) {
                mpp[fruits[left]]--;
                if (mpp[fruits[left]] == 0) {
                    mpp.erase(fruits[left]); 
                }
                left++;
                total--;
            }
            maxi = max(maxi, total);
        }
        return maxi;
    }
};
```
