# Problem: Count Digits

**URL:** [Count Digits – GFG](https://www.geeksforgeeks.org/problems/count-digits-1606889545/1)  
**Statement:** Given a natural number `n`, find the number of digits in it and return the count.

---
### ✅ Solution 1 – Using Loop

```cpp
int countDigits(int n) {
    if (n == 0 || n < 10) {
        return 1;
    }

    int cnt = 0;
    while (n != 0) {
        n = n / 10;
        cnt++;
    }
    return cnt;
}
```
### ✅ Solution 2 – Using Recursion

```cpp
int countDigits(int n) {
    if (n / 10 == 0) {
        return 1;
    }
    return 1 + countDigits(n / 10);
}
```
