# Problem: Replace Elements with Greatest Element on Right Side  

**URL:** [Replace Elements with Greatest Element on Right Side – LeetCode](https://leetcode.com/problems/replace-elements-with-greatest-element-on-right-side/)  
**Statement:** Given an array `arr`, replace every element in that array with the greatest element among the elements to its right, and replace the last element with `-1`.  

After doing so, return the array.  

---
### ✅ Solution – Using Reverse Traversal  
```cpp
class Solution {
public:
    vector<int> replaceElements(vector<int>& arr) {
        int len = arr.size() - 1;
        int max = -1;
        for (int i = len; i >= 0; i--) {
            int temp = arr[i];
            arr[i] = max;
            if (temp > max) {
                max = temp;
            }
        }
        return arr;
    }
};
```