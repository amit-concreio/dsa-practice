# Problem: Maximum Ascending Subarray Sum  

**URL:** [1800 Maximum Ascending Subarray Sum – LeetCode](https://leetcode.com/problems/maximum-ascending-subarray-sum/description/)  

**Statement:**  
You are given an array of positive integers `nums`.  
Return the maximum possible sum of a **strictly increasing subarray** in `nums`.  

A subarray is a contiguous sequence of numbers in an array.  

---

### ✅ Solution – Linear Scan  
We maintain a running sum for the current strictly increasing subarray.  
- If `nums[i] > nums[i-1]`, continue the subarray by adding `nums[i]`.  
- Otherwise, reset the running sum to `nums[i]`.  
At each step, update the maximum sum found so far.  

---

### C++ Code
```cpp
class Solution {
public:
    int maxAscendingSum(vector<int>& nums) {
        int sum = nums[0];
        int ans = nums[0];

        for (int i = 1; i < nums.size(); i++) {
            if (nums[i] > nums[i - 1]) {
                sum += nums[i];  // continue increasing subarray
            } else {
                sum = nums[i];   // reset sum
            }
            ans = max(ans, sum);
        }
        return ans;
    }
};
