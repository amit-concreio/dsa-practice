# Problem: Score of a String  

**URL:** [3110 Score of a String – LeetCode](https://leetcode.com/problems/score-of-a-string/description/)  
**Statement:** You are given a string `s`. The score of a string is defined as the sum of the absolute differences between the ASCII values of adjacent characters.  

Return the score of `s`.  
---

### ✅ Solution – Iterative Calculation  
```cpp
class Solution {
public:
    int scoreOfString(string s) {
        int ans = 0;

        for (int i = 0; i < s.size() - 1; i++) {
            ans += abs((int)s[i] - (int)s[i + 1]);
        }
        return ans;
    }
};
```