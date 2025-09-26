# Problem: Longest Common Prefix  

**URL:** [14 Longest Common Prefix – LeetCode](https://leetcode.com/problems/longest-common-prefix/)  
**Statement:** Write a function to find the longest common prefix string amongst an array of strings.  

If there is no common prefix, return an empty string `""`.  

---
### ✅ Solution – Horizontal Scanning  
```cpp
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
        if (strs.empty())
            return "";

        string prefix = strs[0];

        for (int i = 1; i < strs.size(); i++) {
            int j = 0;

            while (j < prefix.size() && j < strs[i].size() &&
                   prefix[j] == strs[i][j]) {
                j++;
            }

            prefix = prefix.substr(0, j);

            if (prefix.empty())
                return "";
        }

        return prefix;
    }
};
