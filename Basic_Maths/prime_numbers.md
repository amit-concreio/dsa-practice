# Problem: Prime Number  

**URL:** [Prime Number – GFG](https://www.geeksforgeeks.org/problems/prime-number2314/1)  
**Statement:** Given a number `n`, determine whether it is a prime number or not.   
---
#### ✅ Solution – Optimized Trial Division  
```cpp
class Solution {
  public:
    bool isPrime(int n) {
        if (n <= 1) return false;
        if (n <= 3) return true;
        
        if (n % 2 == 0 || n % 3 == 0) return false;
        
        for (int i = 5; i * i <= n; i += 6) {
            if (n % i == 0 || n % (i + 2) == 0) return false;
        }
        return true;
    }
};
```

### Optimized Prime Checking Explanation
### We want to determine whether a number `n` is **prime** efficiently.
### 1. Why check `i * i <= n` instead of `i <= n`?

- If `n` has a divisor greater than `√n`, then the corresponding pair divisor must be **smaller than `√n`**.  
- Example: For `n = 36`, `√n = 6`.
  - Divisors are `(2, 18)`, `(3, 12)`, `(4, 9)`, `(6, 6)`.
  - Notice: once we pass 6, the other divisor in the pair is already smaller.
- So it’s enough to check divisors only **up to `√n`**.

### ✅ This reduces time complexity from `O(n)` to `O(√n)`.
---

### 2. Why increment by `6` (`i += 6`)?

- All prime numbers greater than 3 can be written in the form: 6k ± 1
where `k` is an integer.

- Why?  
Any integer `n` can be expressed as one of:
6k, 6k+1, 6k+2, 6k+3, 6k+4, 6k+5

- `6k` → divisible by 2 or 3  
- `6k+2` → divisible by 2  
- `6k+3` → divisible by 3  
- `6k+4` → divisible by 2  
- So only `6k+1` and `6k+5 (which is 6k-1)` can possibly be prime.

### ✅ Therefore, we only need to check divisibility for numbers of the form `6k ± 1`.  
### This skips unnecessary checks.
---

### 3. Why check both `n % i == 0` and `n % (i + 2) == 0`?

- Since we are checking numbers of the form `6k ± 1`, within each loop:
- `i` represents `6k - 1`
- `i + 2` represents `6k + 1`

- Example when `k = 1`:  
- `i = 5 (6*1 - 1)`  
- `i + 2 = 7 (6*1 + 1)`

- This way, in each iteration, we check both possible prime candidates around a multiple of 6.
- This halves the number of iterations again.
---
