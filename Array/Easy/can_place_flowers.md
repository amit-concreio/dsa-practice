# Problem: Can Place Flowers  

**URL:** [605 Can Place Flowers – LeetCode](https://leetcode.com/problems/can-place-flowers/)  
**Statement:**  
You are given a flowerbed (an array of `0` and `1`), where:  
- `0` → empty plot  
- `1` → already planted  

Rules:  
- No two flowers can be planted in adjacent plots.  
- Return `true` if you can plant `n` flowers without breaking the rules, otherwise `false`.  

---

### ✅ Solution – Greedy Placement  
```cpp
class Solution {
public:
    bool canPlaceFlowers(vector<int>& flowerbed, int n) {
        int len = flowerbed.size();
        int cnt = 0;

        for (int i = 0; i < len; i++) {
            if (flowerbed[i] == 0) {
                int left = (i == 0) ? 0 : flowerbed[i - 1];
                int right = (i == len - 1) ? 0 : flowerbed[i + 1];

                if (left == 0 && right == 0) {
                    flowerbed[i] = 1; // place a flower
                    cnt++;
                    if (cnt >= n) return true;
                }
            }
        }
        return cnt >= n;
    }
};
```