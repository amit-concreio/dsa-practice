# Problem: Armstrong Numbers  

**URL:** [Armstrong Numbers – GFG](https://www.geeksforgeeks.org/problems/armstrong-numbers2727/1)  
**Statement:** You are given a 3-digit number `n`, find whether it is an **Armstrong number** or not.  

An Armstrong number of three digits is a number such that the sum of the cubes of its digits is equal to the number itself.  

Example:  
`371` is an Armstrong number since `3³ + 7³ + 1³ = 371`.  

---
### ✅ Solution – Digit Extraction + Power  
```cpp
class Solution {
  public:
    bool armstrongNumber(int n) {
        int ans  = 0;
        int orig = n;
        
        while (n > 0) {
            int temp = n % 10;
            n /= 10;
            ans += pow(temp, 3);
        }
        
        return orig == ans;
    }
};
```