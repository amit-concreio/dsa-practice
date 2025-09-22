# Problem: Concatenation of Array  

**URL:** [1929 Concatenation of Array – LeetCode](https://leetcode.com/problems/concatenation-of-array/)  
**Statement:** Given an integer array `nums` of length `n`, you want to create an array `ans` of length `2n` where:  

- `ans[i] == nums[i]`  
- `ans[i + n] == nums[i]` for `0 <= i < n`  

Specifically, `ans` is the concatenation of two `nums` arrays.  

Return the array `ans`.  
---

### ✅ Solution 1 – Using `insert()`  
```cpp
class Solution {
public:
    vector<int> getConcatenation(vector<int>& nums) {
        //Write your code here...
        vector<int> ans;
        ans.insert(ans.end(), nums.begin(), nums.end());
        ans.insert(ans.end(), nums.begin(), nums.end());
        return ans;
    }
};
```

### ✅ Solution 2 – Using `Loop`  
```cpp
class Solution {
public:
    vector<int> getConcatenation(vector<int>& nums) {
        //Write your code here...
        int len = nums.size();
       vector<int> ans(2*len, 0);
        for(int i = 0; i < len; i++) {
            ans[i] = nums[i];
            ans[i + len] = nums[i];
        }
        return ans;

    }
};
```