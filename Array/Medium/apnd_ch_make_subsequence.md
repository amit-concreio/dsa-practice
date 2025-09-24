# Problem: Append Characters to String to Make Subsequence  

**URL:** [2486 Append Characters to String to Make Subsequence – LeetCode](https://leetcode.com/problems/append-characters-to-string-to-make-subsequence/)  
**Statement:** You are given two strings `s` and `t` consisting of only lowercase English letters.  

Return the minimum number of characters that need to be appended to the end of `s` so that `t` becomes a subsequence of `s`.  

A subsequence is a string that can be derived from another string by deleting some or no characters without changing the order of the remaining characters.  

---
### ✅ Solution – Two Pointers  
```cpp
class Solution {
public:
    int appendCharacters(string s, string t) {
        int i = 0;
        int j = 0;
        int len1 = s.size(); 
        int len2 = t.size();

        while(i < len1 && j < len2) {
            if(s[i] == t[j]) {
                j++;
            }
            i++;
        }

        return len2 - j;
    }
};
```