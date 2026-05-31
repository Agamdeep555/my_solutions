# container with most water/submissions/2018485545

**Platform:** LeetCode  
**Date:** 2026-05-31  

## Solution

```
class Solution {
public:
    int maxArea(vector<int>& height) {
        int i = 0;
        int j = height.size()-1;
        int maxi = 0;
        int water;
        while(i<j){

            water = min(height[i],height[j])*(j-i);

            maxi = max(maxi,water);

            if(height[i]<height[j]){
                i++;
            }
            else{
                j--;
            }
        }
        return maxi;
    }
};
```
