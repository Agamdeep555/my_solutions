# rotting oranges/submissions/2063840749

**Platform:** LeetCode  
**Date:** 2026-07-11  

## Solution

```
class Solution {
public:
    int func(vector<vector<int>> &vis , vector<vector<int>>& grid, int n, int m){
        queue<pair<pair<int,int>, int>> q;
        int time = 0;
        for(int i=0;i<n;i++){
            for(int j=0;j<m;j++){
                if(vis[i][j]==2){
                    q.push({{i,j},0});
                }
            }
        }


        while(!q.empty()){
            int row = q.front().first.first;
            int col = q.front().first.second;

            time = q.front().second;
            q.pop();

            int nrow = row+1;
            int ncol = col;
            if(nrow<n && nrow>=0 && ncol<m && ncol>=0 && grid[nrow][ncol]==1 && vis[nrow][ncol]!=2){
                q.push({{nrow,ncol},time+1});
                vis[nrow][ncol] = 2;

            }

            int nrow2 = row-1;
            int ncol2 = col;
            if(nrow2<n && nrow2>=0 && ncol2<m && ncol2>=0 && grid[nrow2][ncol2]==1 && vis[nrow2][ncol2]!=2){
                q.push({{nrow2,ncol2},time+1});
                vis[nrow2][ncol2] = 2;

            }

            int nrow3 = row;
            int ncol3 = col+1;
            if(nrow3<n && nrow3>=0 && ncol3<m && ncol3>=0 && grid[nrow3][ncol3]==1 && vis[nrow3][ncol3]!=2){
                q.push({{nrow3,ncol3},time+1});
                vis[nrow3][ncol3] = 2;

            }

            int nrow4 = row;
            int ncol4 = col-1;
            if(nrow4<n && nrow4>=0 && ncol4<m && ncol4>=0 && grid[nrow4][ncol4]==1 && vis[nrow4][ncol4]!=2){
                q.push({{nrow4,ncol4},time+1});
                vis[nrow4][ncol4] = 2;

            }

        }
        return time;

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
        
    
        int time = func(vis,grid,n,m);

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < m; j++) {
                if (grid[i][j] == 1 && vis[i][j] != 2) {
                    return -1;
                }
            }
        }
        return time;
    }
};
```
