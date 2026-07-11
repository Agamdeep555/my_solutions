# Explanation

**Platform:** LeetCode  
**Date:** 2026-07-11  

## Solution

```
class Solution {
public:
    void bfs()
    int findCircleNum(vector<vector<int>>& isConnected) {
        vector<int> adj;
        int n  = isConnected.size();
        int m = isConnected[0].size();
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(isConnected[i][j]==1 && i!=j){
                    adj[i].push_back(j);
                    adj[j].push_bback(i);
                }
            }
        }
    }
};
```
