# online stock span/submissions/2042427577

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class StockSpanner {
public:
    vector<int> arr;
    int i=0;
    StockSpanner() {
        
    }
    
    int next(int price) {
        int cnt = 0;
        if(i==0){
            i=1;
            arr.push_back(price);
            return 1;
        }
        else{
            arr.push_back(price);
            for(int j=i;j>=0;j--){
                if(arr[j]<=price){
                    cnt++;
                }
                else{
                    break;
                }
            }
            i++;
        }
        return cnt;

    }
};

/**
 * Your StockSpanner object will be instantiated and called as such:
 * StockSpanner* obj = new StockSpanner();
 * int param_1 = obj->next(price);
 */
```
