# Problem: Max Consecutive Ones  

**URL:** [485 Max Consecutive Ones – LeetCode](https://leetcode.com/problems/max-consecutive-ones/)  
**Statement:** Given a binary array `nums`, return the maximum number of consecutive `1`s in the array.  

---
### ✅ Solution – Linear Scan  
```cpp
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int maxCnt = 0;
        int cnt = 0;

        for (int i = 0; i < nums.size(); i++) {
            if (nums[i] == 1) {
                cnt++;
            } else {
                maxCnt = max(cnt, maxCnt);
                cnt = 0;
            }
        }

        return max(maxCnt, cnt);
    }
};
```