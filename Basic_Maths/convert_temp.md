# Problem: Convert the Temperature  

**URL:** [2469 Convert the Temperature – LeetCode](https://leetcode.com/problems/convert-the-temperature/description/?envType=problem-list-v2&envId=math)  
**Statement:** You are given a non-negative floating point number `celsius` (rounded to two decimal places), that denotes the temperature in Celsius.  

You should convert Celsius into **Kelvin** and **Fahrenheit** and return it as an array `ans = [kelvin, fahrenheit]`.  

Return the array `ans`. Answers within `10^-5` of the actual answer will be accepted.  

**Note:**  
- Kelvin = `Celsius + 273.15`  
- Fahrenheit = `Celsius * 1.80 + 32.00`  
---

### ✅ Solution – Direct Conversion  
```cpp
class Solution {
public:
    vector<double> convertTemperature(double celsius) {
        // K = C + 273.15
        // F = (C × 9/5) + 32
        return {celsius + 273.15, (celsius * 9) / 5 + 32};
    }
};
```