# Problem: Kth Distinct String in an Array  

**URL:** [Kth Distinct String in an Array – LeetCode](https://leetcode.com/problems/kth-distinct-string-in-an-array/description/)  

**Statement:**  
A **distinct string** is a string that is present only once in an array.  

Given an array of strings `arr`, and an integer `k`, return the **kth distinct string** present in `arr`.  
- If there are fewer than `k` distinct strings, return an empty string `""`.  
- Strings are considered **in the order they appear** in the array.  

---

### ✅ Solution – Hash Map + Order Tracking  
1. Use a hash map to count the frequency of each string.  
2. Traverse the array again to maintain the order.  
3. Count distinct strings, and return the `kth` one.  

---

### C++ Code
```cpp
class Solution {
public:
    string kthDistinct(vector<string>& arr, int k) {
        unordered_map<string, int> mp;

        // Count frequency of each string
        for (int i = 0; i < arr.size(); i++) {
            mp[arr[i]]++;
        }


        int cnt = 0;

        // Traverse again to maintain order
        for (int i = 0; i < arr.size(); i++) {
            if (mp[arr[i]] == 1) {
                cnt++;
                if (cnt == k)
                    return arr[i];
            }
        }
        return "";
    }
};
```