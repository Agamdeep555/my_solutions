# substring with concatenation of all words/description

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    vector<int> findSubstring(string s, vector<string>& words) {
        int wlen = words[1].size();

        unordered_map<string,int> mpp;

        for(int i=0;i<words.size();i++){
            mpp[words[i]]++;
        }
        int cnt=1;
        string str;
        for(int r = 0;r<s.size();r++){

            str += s[r];
            cnt = str.size();
            if(cnt==wlen){
                if(mpp.find(str) != mpp.end()){
                    mpp[str]++;
                }
                str.empty();
            }
            for(auto it: mpp){
                
                if(it.second == ){

                }
            }
        }
    }
};
```
