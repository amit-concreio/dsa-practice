# Problem: Group Anagrams  

**URL:** [49 Group Anagrams – LeetCode](https://leetcode.com/problems/group-anagrams/)  
**Statement:** Given an array of strings `strs`, group the anagrams together. You can return the answer in any order.  

---
### ✅ Solution – Hash Map with Sorted Key  
```cpp
class Solution {
public:
    vector<vector<string>> groupAnagrams(vector<string>& strs) {
        vector<vector<string>> ans;
        unordered_map<string, vector<string>> mp;

        for (string s : strs) {
            string key = s;
            sort(key.begin(), key.end());
            mp[key].push_back(s);
        }

        for (auto &s : mp) {
            ans.push_back(s.second);
        }

        return ans;
    }
};
```