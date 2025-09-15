# Problem: Divisible and Non-divisible Sums Difference  

**URL:** [2894 Divisible and Non-divisible Sums Difference – LeetCode](https://leetcode.com/problems/divisible-and-non-divisible-sums-difference/description/?envType=problem-list-v2&envId=math)  
**Statement:** Given two integers `n` and `m`, find the difference between:  

- The sum of all integers from `1` to `n` that are **not divisible** by `m`.  
- The sum of all integers from `1` to `n` that **are divisible** by `m`.  

Formally, return:  

\[
\left(\sum_{i=1}^{n} i \;|\; i \% m \neq 0\right) \;-\; \left(\sum_{i=1}^{n} i \;|\; i \% m = 0\right)
\]  
---

### ✅ Solution – Iterative Calculation  
```cpp
class Solution {
public:
    int differenceOfSums(int n, int m) {
        int a = 0;
        int b = 0;

        for (int i = 1; i <= n; i++) {
            if (i % m == 0) {
                b += i;
            } else {
                a += i;
            }
        }

        return a - b;
    }
};
```