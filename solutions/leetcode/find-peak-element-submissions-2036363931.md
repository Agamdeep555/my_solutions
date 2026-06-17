# find peak element/submissions/2036363931

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int findPeakElement(vector<int>& nums) {
        if(nums.size()==1) return 0;

        int n = nums.size()-1;
        if(nums[0]>nums[1]) return 0;
        if(nums[n]>nums[n-2]) return n-1;

        int s = 1;
        int e = nums.size()-2;

        while(s<=e){
            int mid = s+(e-s)/2;
            
            if( nums[mid]>nums[mid+1] && nums[mid]>nums[mid-1]){
                return mid;
            }
            if(nums[mid]<nums[mid+1]){
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
