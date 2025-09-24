# Problem: Two Sum  

**URL:** [1 Two Sum – LeetCode](https://leetcode.com/problems/two-sum/)  
**Statement:** Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.  

You may assume that each input would have exactly one solution, and you may not use the same element twice.  

You can return the answer in any order.  

---
### ✅ Solution – Hash Map  
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> mp;

        for (int i = 0; i < nums.size(); i++) {
            int reqNum = target - nums[i];

            if (mp.find(reqNum) != mp.end()) {
                return {mp[reqNum], i};
            } else {
                mp[nums[i]] = i;
            }
        }

        return {};
    }
};
```
