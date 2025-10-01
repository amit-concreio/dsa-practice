# Problem: Maximum Difference Between Even and Odd Frequency I  

**URL:** [3442 Maximum Difference Between Even and Odd Frequency I – LeetCode](https://leetcode.com/problems/maximum-difference-between-even-and-odd-frequency-i/)  
**Statement:** You are given a string `s` consisting of lowercase English letters.  

Your task is to find the maximum difference `diff = freq(a1) - freq(a2)` between the frequency of characters `a1` and `a2` in the string such that:  
- `a1` has an **odd frequency** in the string.  
- `a2` has an **even frequency** in the string.  

Return this maximum difference.  

---
### ✅ Solution – Frequency Counting  
```cpp
class Solution {
public:
    int maxDifference(string s) {
        unordered_map<char, int> mp;

        for (int i = 0; i < s.size(); i++) {
            char ch = s[i];
            mp[ch]++;
        }

        vector<int> odds;
        vector<int> evens;

        for (auto x : mp) {
            if (x.second % 2 == 0) {
                evens.push_back(x.second);
            } else {
                odds.push_back(x.second);
            }
        }

        int diff = INT_MIN;

        for (int o : odds) {
            for (int e : evens) {
                diff = max(diff, o - e);
            }
        }

        return diff;
    }
};
```