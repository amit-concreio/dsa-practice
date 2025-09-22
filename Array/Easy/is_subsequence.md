# Problem: Is Subsequence  

**URL:** [392 Is Subsequence – LeetCode](https://leetcode.com/problems/is-subsequence/)  
**Statement:** Given two strings `s` and `t`, return true if `s` is a subsequence of `t`, or false otherwise.  

A subsequence of a string is a new string that is formed from the original string by deleting some (can be none) of the characters without disturbing the relative positions of the remaining characters. (i.e., `"ace"` is a subsequence of `"abcde"` while `"aec"` is not).  
---

### ✅ Solution – Two Pointers  
```cpp
class Solution {
public:
    bool isSubsequence(string s, string t) {
        int i = 0;
        int j = 0;

        int len1 = s.size();
        int len2 = t.size();

        while (i < len1 && j < len2) {
            if (s[i] == t[j]) {
                i++;
            }
            j++;
        }

        return i == len1;
    }
};
```