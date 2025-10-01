# Problem: Majority Element  

**URL:** [169 Majority Element – LeetCode](https://leetcode.com/problems/majority-element/)  
**Statement:**  
Given an array `nums` of size `n`, return the **majority element**.  
- The majority element is the element that appears **more than ⌊n / 2⌋ times**.  
- You may assume the majority element **always exists**.  

---

### ✅ Solution – HashMap Counting  
```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        unordered_map<int, int> mp;

        for (int i = 0; i < nums.size(); i++) {
            mp[nums[i]]++;
        }

        int len = nums.size() / 2;

        for (auto x : mp) {
            if (x.second > len) return x.first;
        }

        return -1;  
    }
};
```