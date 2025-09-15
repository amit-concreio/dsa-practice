# Problem: Sum 1 to n Divisors  

**URL:** [Sum of All Divisors from 1 to n – GFG](https://www.geeksforgeeks.org/problems/sum-of-all-divisors-from-1-to-n4738/1)  
**Statement:** Given a positive integer `n`, the task is to find the value of  

\[
\sum_{i=1}^{n} F(i)
\]  

where `F(i)` is defined as the sum of all divisors of `i`.  

---
### ✅ Solution – Using Divisor Contribution  
```cpp
class Solution {
  public:
    long long sumOfDivisors(long long n) {
        long long ans = 0;
        
        for (int i = 1; i <= n; i++) {
            ans += (n / (long long)i) * i;
        }
        
        return ans;
    }
};
```
## 🔎 Key Insight

Instead of computing divisors of every number `i`, notice that each divisor `d` appears multiple times.

- Divisor `1` divides all numbers `1..n` → contributes `1 * ⌊n/1⌋`
- Divisor `2` divides every 2nd number → contributes `2 * ⌊n/2⌋`
- Divisor `3` divides every 3rd number → contributes `3 * ⌊n/3⌋`
- …
- Divisor `d` divides all multiples of `d` → contributes:

\[
d \times \left\lfloor \frac{n}{d} \right\rfloor
\]

---

## ✅ Final Formula

\[
\sum_{i=1}^{n} F(i) \;=\; \sum_{d=1}^{n} d \times \left\lfloor \frac{n}{d} \right\rfloor
\]

---

## 📝 Example: n = 8

First compute `F(i)` directly:

- F(1) = 1  
- F(2) = 1+2 = 3  
- F(3) = 1+3 = 4  
- F(4) = 1+2+4 = 7  
- F(5) = 1+5 = 6  
- F(6) = 1+2+3+6 = 12  
- F(7) = 1+7 = 8  
- F(8) = 1+2+4+8 = 15  

**Total = 56**

---

### Now apply the formula:

\[
\sum_{d=1}^{8} d \times \left\lfloor \frac{8}{d} \right\rfloor
\]

- d=1 → 1 × (8/1) = 1 × 8 = 8  
- d=2 → 2 × (8/2) = 2 × 4 = 8  
- d=3 → 3 × (8/3) = 3 × 2 = 6  
- d=4 → 4 × (8/4) = 4 × 2 = 8  
- d=5 → 5 × (8/5) = 5 × 1 = 5  
- d=6 → 6 × (8/6) = 6 × 1 = 6  
- d=7 → 7 × (8/7) = 7 × 1 = 7  
- d=8 → 8 × (8/8) = 8 × 1 = 8  

**Total = 56 ✅**

