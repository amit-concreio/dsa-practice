# Problem: Remove Element  

**URL:** [27 Remove Element – LeetCode](https://leetcode.com/problems/remove-element/)  
**Statement:** Given an integer array `nums` and an integer `val`, remove all occurrences of `val` in `nums` in-place. The order of the elements may be changed. Then return the number of elements in `nums` which are not equal to `val`.  

Consider the number of elements in `nums` which are not equal to `val` be `k`, to get accepted, you need to do the following things:  
- Change the array `nums` such that the first `k` elements of `nums` contain the elements which are not equal to `val`.  
- The remaining elements of `nums` are not important as well as the size of `nums`.  
- Return `k`.  

---
### ✅ Solution – Two Pointers  
```cpp
class Solution {
public:
    int removeElement(vector<int>& nums, int val) {
        if(nums.empty()) return 0;
        
        int i = 0;
        int j = nums.size() - 1;

        while(i <= j) {
            if(nums[i] != val) {
                i++;
            } else {
                nums[i] = nums[j];
                j--;
            }
        }

        return j + 1;
    }
};
```