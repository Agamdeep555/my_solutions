# rotting oranges/submissions/1608721696

**Platform:** LeetCode  
**Date:** 2026-07-11  

## Solution

```
class Solution {
public:
    void func(vector<vector<int>> &vis , vector<vector<int>>& grid, int t, int n, int m){
        queue<pair<pair<int,int>, int>> q;

        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(vis[i][j]==2){
                    q.push({{i,j},t});
                }
            }
        }


        while(!q.empty()){
            int row = q.front().first.first;
            int col = q.front().first.second;

            int time = q.front().second;
            q.pop();

            int nrow = row+1;
            int ncol = col;
            if(nrow<n && nrow>=0 && ncol<m && ncol>=0 && grid[i][j]==1 && vis[i][j]!=2){
                q.push()
            }

        }

    }
    int orangesRotting(vector<vector<int>>& grid) {
        int n = grid.size();
        int m = grid[0].size();
        vector<vector<int>> vis(n, vector<int>(m,0));

        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(grid[i][j]==2){
                    vis[i][j]=2;
                }
            }
        }
        
        int t = 0;
        func(vis,grid,t,n,m);
        return t;
    }
};
```
