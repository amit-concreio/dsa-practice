# Problem: Valid Anagram  

**URL:** [Valid Anagram – LeetCode](https://leetcode.com/problems/valid-anagram/description/)  
**Statement:** Given two strings `s` and `t`, return `true` if `t` is an anagram of `s`, and `false` otherwise.  
---

### ✅ Solution – Frequency Count  
```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        if (s.length() != t.length())
            return false;

        vector<int> freq(26, 0);

        for (char ch : s) {
            freq[ch - 'a']++;
        }

        for (char ch : t) {
            freq[ch - 'a']--;
        }

        for (int i = 0; i < 26; i++) {
            if (freq[i] != 0)
                return false;
        }

        return true;
    }
};
```