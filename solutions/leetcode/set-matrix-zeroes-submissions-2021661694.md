# set matrix zeroes/submissions/2021661694

**Platform:** LeetCode  
**Date:** 2026-06-03  

## Solution

```
    class Solution {
    public:
        void setZeroes(vector<vector<int>>& matrix) {
            int m = matrix.size();
            int n = matrix[0].size();

            for(int i=0;i<m;i++){
                for(int j=0;j<n;j++){
                    if(matrix[i][j]==0){
                        int r = i;
                        while(r>=0){
                            if(matrix[r][j]!=0){
                                matrix[r][j]=-99999;
                            }
                            
                            if(r==0) break;
                            r--;
                        }
                        int l = i;
                        while(l<m){
                            if(matrix[l][j]!=0){
                                matrix[l][j]=-99999;
                            }
                            
                            if(l==m-1) break;
                            l++;
                        }
                        int m = j;
                        while(m>=0){
                            if(matrix[i][m]!=0){
                                matrix[i][m]=-99999;
                            }
                            
                            if(m==0) break;
                            m--;
                        }
                        int x = j;
                        while(x<n){
                            if(matrix[i][x]!=0){
                                matrix[i][x]=-99999;
                            }
                            
                            if(x==n-1) break;
                            x++;
                        }
                    }
                }
            }
            for(int i=0;i<m;i++){
                for(int j=0;j<n;j++){
                    if(matrix[i][j]==-99999){
                        matrix[i][j]=0;
                    }
                }
            }
        }
    };
```
