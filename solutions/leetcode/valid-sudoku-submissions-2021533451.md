# valid sudoku/submissions/2021533451

**Platform:** LeetCode  
**Date:** 2026-06-03  

## Solution

```
class Solution {
public:
    bool isValidSudoku(vector<vector<char>>& board) {
        for(int i=0;i<9;i++){
            unordered_map<int,int> mpp;
            for(int j=0;j<9;j++){
                if(board[i][j] == '.') continue;
                mpp[board[i][j]]++;
                if(mpp[board[i][j]]>1){
                    return false;
                }
            }
        }
        for(int i=0;i<9;i++){
            unordered_map<int,int> mpp;
            for(int j=0;j<9;j++){
                if(board[j][i] == '.') continue;
                mpp[board[j][i]]++;
                if(mpp[board[j][i]]>1){
                    return false;
                }
            }
        }
        for(int k=0;k<9;k=k+3){
            unordered_map<int,int> mpp;
        
        for(int i=0+k;i<3+k;i++){
            for(int j=0;j<3;j++){
                if(board[i][j] == '.') continue;
                mpp[board[i][j]]++;
                if(mpp[board[i][j]]>1){
                    return false;
                }
            }
        }
        }

        for(int k=0;k<9;k=k+3){
            unordered_map<int,int> mpp;
        
        for(int i=0+k;i<3+k;i++){
            for(int j=3;j<6;j++){
                if(board[i][j] == '.') continue;
                mpp[board[i][j]]++;
                if(mpp[board[i][j]]>1){
                    return false;
                }
            }
        }
        }

        for(int k=0;k<9;k=k+3){
            unordered_map<int,int> mpp;
        
        for(int i=0+k;i<3+k;i++){
            for(int j=6;j<9;j++){
                if(board[i][j] == '.') continue;
                mpp[board[i][j]]++;
                if(mpp[board[i][j]]>1){
                    return false;
                }
            }
        }
        }
        return true;
    }
};
```
