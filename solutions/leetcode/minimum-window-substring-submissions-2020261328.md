# minimum window substring/submissions/2020261328

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    string minWindow(string s, string t) {

        if (t.size() > s.size()) {
            return "";
        }

        unordered_map<char, int> need;

        for (int i = 0; i < t.size(); i++) {
            need[t[i]]++;
        }

        unordered_map<char, int> curr;

        int mini = INT_MAX;
        int lind = -1;
        int rind = -1;

        int match = 0;
        int left = 0;
        int req = t.size();

        for (int r = 0; r < s.size(); r++) {

            if (need.find(s[r]) != need.end()) {

                curr[s[r]]++;

                if (curr[s[r]] <= need[s[r]]) {
                    match++;
                }
            }

            while (match == req) {

                int value = r - left + 1;

                if (value < mini) {
                    mini = value;
                    lind = left;
                    rind = r;
                }

                if (need.find(s[left]) != need.end()) {

                    curr[s[left]]--;

                    if (curr[s[left]] < need[s[left]]) {
                        match--;
                    }
                }

                left++;
            }
        }

        if (lind == -1)
            return "";

        return s.substr(lind, mini);
    }
};
```
