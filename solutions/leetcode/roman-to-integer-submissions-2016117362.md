# roman to integer/submissions/2016117362

**Platform:** LeetCode  
**Date:** 2026-05-29  

## Solution

```
class Solution {
    private:
    int func(char c){
        if(c=='I') return 1;
        if(c=='V') return 5;
        if(c=='X') return 10;
        if(c=='L') return 50;
        if(c=='C') return 100;
        if(c=='D') return 500;
        return 1000;
        
    }
public:
    int romanToInt(string s) {

        int sum = 0;

        for(int i = 0; i < s.size(); i++) {

            if(i+1<s.size() && func(s[i])<func(s[i+1])){
                sum = sum-func(s[i]);
            }
            else{
                sum = sum + func(s[i]);
            }
        }

        return sum;
    }
};
```
