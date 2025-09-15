# Problem: Contains Duplicate  

**URL:** [217 Contains Duplicate – LeetCode](https://leetcode.com/problems/contains-duplicate/description/)  
**Statement:** Given an integer array `nums`, return `true` if any value appears at least twice in the array, and return `false` if every element is distinct.  

---
### ✅ Solution – Using Hash Set  
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> ans;

        for (int i = 0; i < nums.size(); i++) {
            if (ans.count(nums[i])) {
                return true;
            }
            ans.insert(nums[i]);
        }

        return false;
    }
};
