# Problem: Palindrome Number  

**URL:** [9 Palindrome Number – LeetCode](https://leetcode.com/problems/palindrome-number/description/?envType=problem-list-v2&envId=math)  
**Statement:** Given an integer `x`, return `true` if `x` is a palindrome, and `false` otherwise.  

---
### ✅ Solution – Reverse Integer Check  
```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        if (x < 0) return false;
        if (x == 0) return true;

        int num = x;
        long long ans = 0;

        while (x > 0) {
            int temp = x % 10;
            ans = ans * 10 + temp;
            x /= 10;
        }

        return num == ans;
    }
};
```