# Problem: LCM and GCD  

**URL:** [LCM and GCD – GFG](https://www.geeksforgeeks.org/problems/lcm-and-gcd4516/1)  
**Statement:** Given two integers `a` and `b`, compute their **LCM** and **GCD** and return an array containing `{LCM, GCD}`.  

---
#### ✅ Solution – Using Euclidean Algorithm  
```cpp
class Solution {
  public:
    // Function to compute GCD (HCF)
    int findHCF(int a, int b) {
        while (b != 0) {
            int rem = a % b;
            a = b;
            b = rem;
        }
        return a;
    }

    vector<int> lcmAndGcd(int a, int b) {
        int hcf = findHCF(a, b);
        int lcm = (a * b) / hcf;
        return {lcm, hcf};
    }
};
```