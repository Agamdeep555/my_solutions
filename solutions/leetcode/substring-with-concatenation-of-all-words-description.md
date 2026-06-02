# substring with concatenation of all words/description

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    vector<int> findSubstring(string s, vector<string>& words) {

        unordered_map<string,int> need;
        for(auto &w : words) need[w]++;

        int wlen = words[0].size();
        int n = words.size();

        vector<int> ans;

        for(int start = 0; start < wlen; start++) {

            unordered_map<string,int> window;
            int left = start;
            int count = 0;

            for(int right = start; right + wlen <= s.size(); right += wlen) {

                string word = s.substr(right, wlen);

                if(need.count(word)) {

                    window[word]++;
                    count++;

                    while(window[word] > need[word]) {
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
