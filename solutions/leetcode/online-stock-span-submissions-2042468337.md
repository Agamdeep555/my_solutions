# online stock span/submissions/2042468337

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class StockSpanner {
public:
    stack<pair<int,int>> st; // {price, index}
    int idx;

    StockSpanner() {
        idx = -1;
    }

    int next(int price) {

        idx++;

        while(!st.empty() && st.top().first <= price) {
            st.pop();
        }

        int pge;

        if(st.empty())
            pge = -1;
        else
            pge = st.top().second;

        int span = idx - pge;

        st.push({price, idx});

        return span;
    }
};
```
