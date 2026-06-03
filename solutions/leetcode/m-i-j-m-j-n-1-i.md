# M[i,j] --> M'[j,N-1-i]

**Platform:** LeetCode  
**Date:** 2026-06-03  

## Solution

```
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {

        int n = matrix.size();
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                swap(matrix[i][j] , matrix[j][i]);
            }
        }

        int j = n-1;
        int i = 0;

        while(i<j){
            for(int k=0;k<n;k++){
                swap(matrix[k][i] , matrix[k][j]);
            }
            i++;
            j--;
        }
    }
};
```
