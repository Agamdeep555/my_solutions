# Intuition

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    vector<int> findSubstring(string s, vector<string>& words) {

        int wlen = words[0].size();
        int n = words.size();

        unordered_map<string,int> mpp;
        for(auto &w : words) {
            mpp[w]++;
        }

        vector<int> ans;

        for(int offset = 0; offset < wlen; offset++) {

            int left = offset;
            int count = 0;

            unordered_map<string,int> window;

            for(int right = offset; right + wlen <= s.size(); right += wlen) {

                string word = s.substr(right, wlen);

                if(mpp.find(word) != mpp.end()) {

                    window[word]++;
                    count++;

                    while(window[word] > mpp[word]) {
                        string leftWord = s.substr(left, wlen);
                        window[leftWord]--;
                        left += wlen;
                        count--;
                    }

                    if(count == n) {
                        ans.push_back(left);

                        string leftWord = s.substr(left, wlen);
                        window[leftWord]--;
                        left += wlen;
                        count--;
                    }
                }
                else {
                    window.clear();
                    count = 0;
                    left = right + wlen;
                }
            }
        }

        return ans;
    }
};
```
