# online stock span/submissions/2042465467

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class StockSpanner {
public:
    stack<pair<int,int>> st;

    StockSpanner() {

    }

    int next(int price) {

        int span = 1;

        while(!st.empty() && st.top().first <= price) {
            span += st.top().second;
            st.pop();
        }

        st.push({price, span});

        return span;
    }
};
```
