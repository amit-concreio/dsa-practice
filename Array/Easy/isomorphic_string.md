# Problem: Isomorphic Strings  

**URL:** [205 Isomorphic Strings – LeetCode](https://leetcode.com/problems/isomorphic-strings/)  
**Statement:** Given two strings `s` and `t`, determine if they are isomorphic.  

Two strings `s` and `t` are isomorphic if the characters in `s` can be replaced to get `t`.  

- All occurrences of a character must be replaced with another character while preserving the order of characters.  
- No two characters may map to the same character, but a character may map to itself.  

---
### ✅ Solution – Mapping with Arrays  
```cpp
class Solution {
public:
    bool isIsomorphic(string s, string t) {
        if(s.size() != t.size()) return false;

        vector<int> a(256, -1);
        vector<int> b(256, -1);

        for (int i = 0; i < s.size(); i++) {
            char c1 = s[i];
            char c2 = t[i];

            if (a[c1] != -1 && a[c1] != c2)
                return false;
            if (b[c2] != -1 && b[c2] != c1)
                return false;

            a[c1] = c2;
            b[c2] = c1;
        }
        return true;
    }
};
```