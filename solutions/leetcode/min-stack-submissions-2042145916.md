# min stack/submissions/2042145916

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class MinStack {
public:
    stack<int> s;
    int mini = INT_MAX;
    int lastmin = -1;
    MinStack() {
        
    }
    
    void push(int value) {
        s.push(value);
        lastmin = mini;
        mini = min(mini,value);
    }
    
    void pop() {
        s.pop();
        mini  = lastmin;
    }
    
    int top() {
        return s.top();
    }
    
    int getMin() {
        return mini;
    }
};

/**
 * Your MinStack object will be instantiated and called as such:
 * MinStack* obj = new MinStack();
 * obj->push(value);
 * obj->pop();
 * int param_3 = obj->top();
 * int param_4 = obj->getMin();
 */
```
