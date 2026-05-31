# How does the submission work

**Platform:** LeetCode  
**Date:** 2026-05-31  

## Solution

```
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        int i = 0;
        int j = numbers.size()-1;
        int sum = -1;
        while(true){
            sum = numbers[i]+numbers[j];
            if(sum > target){
                j--;
            }
            else if(sum < target){
                i++;
            }
            else{
                return {i+1,j+1};
            }
        }
        return {i+1,j+1};

    }
};
```
