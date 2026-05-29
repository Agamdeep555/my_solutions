# gas station/submissions/1741314214

**Platform:** LeetCode  
**Date:** 2026-05-29  

## Solution

```
class Solution {
public:
    int canCompleteCircuit(vector<int>& gas, vector<int>& cost) {
        int n = gas.size();
        for(int i=0;i<gas.size();i++){
            if(gas[i]>=cost[i]){
                int fuel = gas[i];
                int k=gas.size();
                int j=i;
                while(k>0){
                    j = j%n;
    
                    fuel = fuel - cost[j];
                    if(fuel<0) break;
                    k--;

                    if(k==0) return i;
                    j = (j + 1) % n;
                    fuel = fuel + gas[j];
                }
            }
        }
        return -1;
    }
};
```
