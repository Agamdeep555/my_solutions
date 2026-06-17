# sqrtx/submissions/2036390587

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int mySqrt(int x) {
        int s = 0;
        int e = x-1;
        int ans = 0;

        while(s<=e){
            int mid = s+(e-s)/2;
            
            if((long long)mid*mid<=x){
                ans = mid;
                s=mid+1;
            }
            else{
                e=mid-1;
            }
        }
        return ans;
    }
};
```
