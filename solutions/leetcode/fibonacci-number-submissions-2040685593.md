# fibonacci number/submissions/2040685593

**Platform:** LeetCode  
**Date:** 2026-06-21  

## Solution

```
class Solution {
public:
    int func(int n){
        if(n==0) return 0;
        if(n==1) return 1;

        return func(n-1)+func(n-2);
    }
    int fib(int n) {
        return func(n);
    }
};
```
