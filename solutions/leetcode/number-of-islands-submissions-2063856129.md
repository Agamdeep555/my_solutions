# number of islands/submissions/2063856129

**Platform:** LeetCode  
**Date:** 2026-07-11  

## Solution

```
class Solution {
public:
    void dfs(int row, int col, vector<vector<char>>& grid, vector<vector<int>>& vis, int n, int m){
        int drow[] = {-1,0,0,1};
        int dcol[] = {0,-1,1,0};   
        for(int i=0;i<4;i++){
            int nrow = row+drow[i];
            int ncol = col+dcol[i];

            if(nrow<n && ncol<m && nrow>=0 && ncol>=0 && grid[nrow][ncol]=='1' && vis[nrow][ncol]!=1){
                vis[nrow][ncol]=1;
                dfs(nrow,ncol,grid,vis,n,m);
            }
        }
    }
    int numIslands(vector<vector<char>>& grid) {
        int n = grid.size();
        int m = grid[0].size();

        vector<vector<int>> vis(n, vector<int>(m,0));
        int cnt=0;
        for(int i =0;i<n;i++){
            for(int j=0;j<m;j++){
                if(vis[i][j]==0 && grid[i][j]=='1'){
                    vis[i][j]=1;
                    cnt++;
                    dfs(i,j,grid,vis,n,m);
                }
            }
        }
        return cnt;
    }
};
```
