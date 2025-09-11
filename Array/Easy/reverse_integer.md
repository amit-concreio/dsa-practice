# Problem: Reverse Integer  

**URL:** [7 Reverse Integer – LeetCode](https://leetcode.com/problems/reverse-integer/description/)  
**Statement:** Given a signed 32-bit integer `x`, return `x` with its digits reversed. If reversing `x` causes the value to go outside the signed 32-bit integer range `[-2^31, 2^31 - 1]`, then return `0`.  

Assume the environment does not allow storing 64-bit integers (signed or unsigned).  

---
#### ✅ Solution – Using Loop  

```cpp
class Solution {
public:
    int reverse(int x) {
        // Write your code here...
        long long ans = 0;

        while(x != 0) {
            int digit = x%10;
            x = x/10;
    
            ans = ans * 10 + digit;

        }

        if(ans > INT_MAX || ans < INT_MIN) return 0;

        return ans;
    }
};
```