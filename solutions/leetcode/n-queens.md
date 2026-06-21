# n queens

**Platform:** LeetCode  
**Date:** 2026-06-21  

## Solution

```
class Solution {
    private:
    bool issafe(int row , int col , vector<string> &board, int n){
        int drow = row;
        int dcol = col;

        while(row>=0 && col>=0){
            if(board[row][col]=='Q') return false;
            row--;
            col--;
        }

        row = drow;
        col = dcol;

        while(col>=0){
            if(board[row][col]=='Q') return false;
            col--;
        }

        row = drow;
        col = dcol;

        while(row<n && col>=0){
            if(board[row][col]=='Q') return false;
            row++;
            col--;
        }
        return true;
    }

    void func(int col , int n , vector<string> &board , vector<vector<string>> &ans){
        if(col == n){
            ans.push_back(board);
            return;
        }
        for(int row=0;row<n;row++){
            if(issafe(row,col,board,n)){
                board[row][col]='Q';
                func(col+1,n,board,ans);
                board[row][col]='.';
            }
        }

    }
public:
    vector<vector<string>> solveNQueens(int n) {
        vector<vector<string>> ans;
        vector<string> board(n,string(n,'.'));
        func(0,n,board,ans);
        return ans;
    }
};
```
