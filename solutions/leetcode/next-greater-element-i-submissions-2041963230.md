# next greater element i/submissions/2041963230

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
        vector<int> ans;
        for(int i=0;i<nums1.size();i++){
            stack<int> s;
            for(int j=0;j<nums2.size();j++){
                if(nums2[j]==nums1[i]){
                    s.push(nums1[i]);
                }
                if(!s.empty()){
                    if(s.top()<nums2[j]){
                        ans.push_back(nums2[j]);
                        break;
                    }
                }
            }
            if(!s.empty()){
                ans.push_back(-1);
            }
        }
        ans.pop_back();
        return ans;
    }
};
```
