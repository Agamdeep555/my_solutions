# find first and last position of element in sorted array/submissions/2036121348

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int left(vector<int>& nums, int target){
        int s = 0;
        int l = nums.size()-1;
        int ans = -1;
        while(s<=l){
            int mid = s + (l-s)/2;

            if(nums[mid]==target){
                ans = mid;
                l = mid-1;
            }
            else if(nums[mid]<target){
                s = mid+1;
            }
            else{
                l = mid-1;
            }
        }
        return ans;
    }
    int right(vector<int>& nums, int target){
        int s = 0;
        int l = nums.size()-1;
        int ans = -1;
        while(s<=l){
            int mid = s + (l-s)/2;

            if(nums[mid]==target){
                ans = mid;
                s = mid+1;
            }
            else if(nums[mid]<target){
                s = mid+1;
            }
            else{
                l = mid-1;
            }
        }
        return ans;
    }
    vector<int> searchRange(vector<int>& nums, int target) {
        
        int l = left(nums,target);
        int r = right(nums,target);

        return {l,r};
    }
};
```
