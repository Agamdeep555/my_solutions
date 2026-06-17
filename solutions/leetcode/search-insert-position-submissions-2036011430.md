# search insert position/submissions/2036011430

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int ans = nums.size();

        int s = 0;
        int e = nums.size()-1;

        while(s<=e){
            int mid = s + (e-s)/2;
            
            if(nums[mid]==target){
                return mid;
            }
            if(nums[mid]>target){
                ans = mid;
                e= mid-1;
            }
            else{
                s=mid+1;
            }
        }
        return ans;
    }
};
```
