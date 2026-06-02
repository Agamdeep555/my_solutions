# fruit into baskets/submissions/2020316933

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    int totalFruit(vector<int>& fruits) {
        if(fruits.size()==2) return 2;
        if(fruits.size()==1) return 1;
        if(fruits.size()==0) return 0;


        unordered_map<int,int> mpp;
        mpp[fruits[0]]++;
        mpp[fruits[1]]++;
        int maxi = 2;
        int total = 2;
        int left  = 0;
        
        for(int r = 2;r<fruits.size();r++){
            if(mpp.count(fruits[r])!=0){
                total++;
            }
            else{
                mpp[fruits[r]]++;
                mpp[fruits[left]]--;
                left++;
            }
            maxi = max(maxi,total);
        }
        return maxi;
    }
};
```
