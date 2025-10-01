# Problem: Longest Strictly Increasing or Strictly Decreasing Subarray  

**URL:** [3105 Longest Strictly Increasing or Strictly Decreasing Subarray – LeetCode](https://leetcode.com/problems/longest-strictly-increasing-or-strictly-decreasing-subarray/)  

**Statement:**  
You are given an array of integers `nums`.  
Return the length of the longest subarray of `nums` which is either strictly increasing or strictly decreasing.  

---

### ✅ Solution – Sliding Window / Linear Scan  
We keep two counters:  
- `inc` → length of current increasing subarray  
- `dec` → length of current decreasing subarray  

At each step:
- If `nums[i] > nums[i-1]`, we extend the increasing streak and reset the decreasing one.  
- If `nums[i] < nums[i-1]`, we extend the decreasing streak and reset the increasing one.  
- If equal, both streaks reset to `1`.  

The maximum of these values gives the answer.  

---

### C++ Code
```cpp
class Solution {
public:
    int longestMonotonicSubarray(vector<int>& nums) {
        int inc = 1, dec = 1, ans = 1;

        for (int i = 1; i < nums.size(); i++) {
            if (nums[i] > nums[i - 1]) {
                inc++;
                dec = 1;
            } else if (nums[i] < nums[i - 1]) {
                dec++;
                inc = 1;
            } else {
                inc = dec = 1;
            }
            ans = max(ans, max(inc, dec));
        }
        return ans;
    }
};
```