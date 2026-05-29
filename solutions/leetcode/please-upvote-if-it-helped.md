# PLEASE UPVOTE IF IT HELPED

**Platform:** LeetCode  
**Date:** 2026-05-29  

## Solution

```
class RandomizedSet {
    vector<int> v;
    unordered_map<int,int> mpp;
public:
    RandomizedSet() {

    }
    bool search(int val){
        if(mpp.find(val) != mpp.end()){
            return true;
        }
        
        return false;
    }

    bool insert(int val) {
        if(search(val)){
            return false;
        }
        mpp[val] = v.size();
        v.push_back(val);
        return true;

    }

    bool remove(int val) {
        if(!search(val)){
            return false;
        }
        int last = v.back();
        int idx  = mpp[val];

        v[idx] = last;
        mpp[last] = idx;

        mpp.erase(val);
        v.pop_back();
        return true;

        
    }

    int getRandom() {
        int idx = rand() % v.size();
        return v[idx];
    }
};

/**
 * Your RandomizedSet object will be instantiated and called as such:
 * RandomizedSet* obj = new RandomizedSet();
 * bool param_1 = obj->insert(val);
 * bool param_2 = obj->remove(val);
 * int param_3 = obj->getRandom();
 */
```
