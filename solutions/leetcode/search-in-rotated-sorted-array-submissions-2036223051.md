# search in rotated sorted array/submissions/2036223051

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int left(vector<int>& nums, int target,int pivot){
        int s = 0;
        int l;
        if(pivot-1>=0){
            l = pivot-1;
        }

        while(s<=l){
            int mid = s + (l-s)/2;

            if(nums[mid]==target){
                return mid;
            }
            else if(nums[mid]<target){
                s = mid+1;
            }
            else{
                l = mid-1;
            }
        }
        return -1;
    }
    
    int right(vector<int>& nums, int target,int pivot){
        int s = pivot;
        int l = nums.size()-1;

        while(s<=l){
            int mid = s + (l-s)/2;

            if(nums[mid]==target){
                return mid;
            }
            else if(nums[mid]<target){
                s = mid+1;
            }
            else{
                l = mid-1;
            }
        }
        return -1;
    }
    int pivot(vector<int>& nums, int target){
        int s = 0;
        int e = nums.size()-1;

        while(s<e){
            int mid = s+(e-s)/2;

            if(nums[mid]>nums[e]){
                s = mid+1;
            }
            else{
                e = mid;
            }
        }
        return s;
    }
    int search(vector<int>& nums, int target) {
        int val = pivot(nums,target);

        int l = left(nums, target,val);
        int r = right(nums, target,val);

        if(l!=-1){
            return l;
        }
        else if(r!=-1){
            return r;
        }
        else{
            return -1;
        }
    }
};
```
