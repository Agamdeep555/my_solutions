# Hint

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int singleNonDuplicate(vector<int>& nums) {
        if(nums.size()==1) return nums[0];
        int n = nums.size()-1;

        if(nums[0]!=nums[1]) return nums[0];
        if(nums[n]!=nums[n-1]) return nums[n];

        int s = 1;
        int e = n-1;

        while(s<=e){
            int mid = s+(e-s)/2;

            if(nums[mid]!=nums[mid-1] && nums[mid]!=nums[mid+1]){
                return nums[mid];
            }

            if(mid%2==0 && nums[mid]==nums[mid+1] || mid%2==1 && nums[mid]==nums[mid-1]){
                s = mid+1;
            }
            else{
                e = mid-1;
            }
        }
        return -1;
    }
};
```
