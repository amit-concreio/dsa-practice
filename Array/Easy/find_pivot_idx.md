# Problem: Find Pivot Index  

**URL:** [724 Find Pivot Index – LeetCode](https://leetcode.com/problems/find-pivot-index/)  

**Statement:**  
Given an array of integers `nums`, calculate the **pivot index** of this array.  

- The pivot index is the index where the **sum of all numbers strictly to the left** of the index is equal to the **sum of all numbers strictly to the right**.  
- If the index is on the left edge of the array, the left sum is `0`. Similarly, if it is on the right edge, the right sum is `0`.  
- Return the **leftmost pivot index**. If no such index exists, return `-1`.  

---

### ✅ Solution – Prefix Sum Approach  
Compute the total sum of the array, then iterate while maintaining a running left sum.  
- Right sum at index `i` = `totalSum - leftSum - nums[i]`  
- If `leftSum == rightSum`, return index `i`.  

---

### C++ Code
```cpp
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int sum = 0;
        for (int i = 0; i < nums.size(); i++) {
            sum += nums[i];
        }

        int leftSum = 0;
        for (int i = 0; i < nums.size(); i++) {
            int rightSum = sum - leftSum - nums[i];
            if (leftSum == rightSum) {
                return i;
            }
            leftSum += nums[i];
        }
        return -1;
    }
};
```