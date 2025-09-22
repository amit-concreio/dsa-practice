# Problem: Length of Last Word  

**URL:** [58 Length of Last Word – LeetCode](https://leetcode.com/problems/length-of-last-word/)  
**Statement:** Given a string `s` consisting of words and spaces, return the length of the last word in the string.  

A word is a maximal substring consisting of non-space characters only.  

---
### ✅ Solution – Reverse Traversal  
```cpp
class Solution {
public:
    int lengthOfLastWord(string s) {
        int len = s.size();
        int i = len - 1;
        int ans = 0;

        while (i >= 0 && s[i] == ' ') {
            i--;
        }

        while (i >= 0 && s[i] != ' ') {
            i--;
            ans++;
        }

        return ans;
    }
};
