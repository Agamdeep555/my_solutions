# spiral matrix/submissions/2021911119

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    vector<int> spiralOrder(vector<vector<int>>& matrix) {
        int n = matrix.size();
        int m = matrix[0].size();

        vector<int> ans;


        int dir = 0;
        int i=0;
        int j=0;

        vector<vector<int>> vis(n,vector<int> (m,0));
        ans.push_back(matrix[0][0]);
        vis[0][0]=1;

        while(ans.size()<n*m){
            if(dir==0){
                if(j+1<m && vis[i][j+1]==0){
                    j++;
                    ans.push_back(matrix[i][j]);
                    vis[i][j]=1;
                }
                else{
                    dir=1;
                }
            }
            else if(dir==1){
                if(i+1<n && vis[i+1][j]==0){
                    i++;
                    ans.push_back(matrix[i][j]);
                    vis[i][j]=1;
                }
                else{
                    dir=2;
                }
            }
            else if(dir==2){
                if(j-1>=0 && vis[i][j-1]==0){
                    j--;
                    ans.push_back(matrix[i][j]);
                    vis[i][j]=1;
                }
                else{
                    dir=3;
                }
            }
            else{
                if(i-1>=0 && vis[i-1][j]==0){
                    i--;
                    ans.push_back(matrix[i][j]);
                    vis[i][j]=1;
                }
                else{
                    dir=0;
                }
            }
        }
        return ans;
    }
};
```
