# sqrtx/submissions/2036387470

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
class Solution {
public:
    int mySqrt(int x) {
        int s = 0;
        int e = x-1;

        while(s<e){
            int mid = s+(e-s)/2;

            if((long long)mid*mid<=x){
                s=mid+1;
            }
            else{
                e=mid;
            }
        }
        return s-1;
    }
};
```
