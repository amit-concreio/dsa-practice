# Problem: Plus One  

**URL:** [66 Plus One – LeetCode](https://leetcode.com/problems/plus-one/description/?envType=problem-list-v2&envId=math)  
**Statement:** You are given a large integer represented as an integer array `digits`, where each `digits[i]` is the *i-th* digit of the integer.  

The digits are ordered from most significant to least significant in left-to-right order. The large integer does not contain any leading 0's.  

Increment the large integer by one and return the resulting array of digits.  

---
### ✅ Solution – Carry Propagation  
```cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int len = digits.size();

        for (int i = len - 1; i >= 0; i--) {
            if (digits[i] < 9) {
                digits[i]++;
                return digits;
            }
            digits[i] = 0;
        }

        digits.insert(digits.begin(), 1);
        return digits;
    }
};
