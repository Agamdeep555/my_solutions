# find peak element/submissions/2036352645

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int findPeakElement(vector<int>& nums) {
        if(nums.size()==1) return 0;
        int s = 0;
        int e = nums.size()-1;
        // int nums[-1] = INT_MIN;
        // int nums[nums.size()] = INT_MIN;

        while(s<=e){
            int mid = s+(e-s)/2;
            int mini;
            int mini2;
            if(mid+1>=nums.size()){
                mini = INT_MIN;
            }
            else{
                mini = nums[mid+1];
            }

            if(mid-1<0){
                mini2 = INT_MIN;
            }
            else{
                mini2 = nums[mid-1];
            }
            if( nums[mid]>mini && nums[mid]>mini2){
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
