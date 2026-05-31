# Intuition

**Platform:** LeetCode  
**Date:** 2026-05-31  

## Solution

```
class Solution {
public:
    string convert(string s, int numRows) {
        if(numRows == 1) return s;

        vector<string> rows(numRows);
        int num = numRows;
        int j = 0;
        bool forward = true;

        for(int i=0;i<s.size();i++){

            if(j>=0 && j<num && forward == true){
                rows[j] += s[i];
                j++;
                if(j==num){
                    forward = false;
                    j=j-2;
                }
            }
            else if(j<num && forward == false){
                //if(j==num) j=j-2;
                rows[j] += s[i];
                j--;
                if(j<0){
                    forward = true;
                    j=j+2;
                }
            }
        }
        string ans;
        for(int i=0;i<num;i++){
            ans += rows[i];
        }

        return ans;
    }
};
```
