# h index/submissions/2014895498

**Platform:** LeetCode  
**Date:** 2026-05-27  

## Solution

```
class Solution {
public:
    int hIndex(vector<int>& citations) {
        int count=0;
        for(int i=0;i<citations.size();i++){
            if(citations[i]>=3){
                count++;
            }
        }
        return count;
    }
};
```
