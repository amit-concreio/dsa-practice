# Problem: String Matching in an Array  

**URL:** [1408 String Matching in an Array – LeetCode](https://leetcode.com/problems/string-matching-in-an-array/)  
**Statement:** Given an array of strings `words`, return all strings in `words` that are a substring of another word. You can return the answer in any order.  

---
### ✅ Solution – Brute Force Substring Search  
```cpp
class Solution {
public:
    vector<string> stringMatching(vector<string>& words) {
        vector<string> result;

        int len = words.size();

        for(int i = 0; i < len; i++) {
            for(int j = 0; j < len; j++) {
                if(i == j) continue;
                string s = words[j];
                if(s.find(words[i]) != string::npos) {
                    result.push_back(words[i]);
                    break;
                }
            }
        }
        return result;
    }
};
```