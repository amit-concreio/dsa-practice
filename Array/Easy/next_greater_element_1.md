# Problem: Next Greater Element I  

**URL:** [Next Greater Element I – LeetCode](https://leetcode.com/problems/next-greater-element-i/)  
**Statement:** The next greater element of some element `x` in an array is the first greater element that is to the right of `x` in the same array.  

You are given two distinct 0-indexed integer arrays `nums1` and `nums2`, where `nums1` is a subset of `nums2`.  

For each `0 <= i < nums1.length`, find the index `j` such that `nums1[i] == nums2[j]` and determine the next greater element of `nums2[j]` in `nums2`. If there is no next greater element, then the answer for this query is `-1`.  

Return an array `ans` of length `nums1.length` such that `ans[i]` is the next greater element as described above.  

---
### ✅ Solution 1 – Brute Force  
```cpp
class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
        int len1 = nums1.size();
        int len2 = nums2.size();

        vector<int> ans(len1, -1);

        for (int i = 0; i < len1; i++) {
            int temp = nums1[i];

            for (int j = 0; j < len2 - 1; j++) {
                if (nums2[j] == temp) {
                    for (int k = j + 1; k < len2; k++) {
                        if (nums2[k] > temp) {
                            ans[i] = nums2[k];
                            break;
                        }
                    }
                    break;
                }
            }
        }

        return ans;
    }
};
```

### ✅ Solution 2 – using Stack & HashMap  
```cpp
class Solution {
public:
    vector<int> nextGreaterElement(vector<int>& nums1, vector<int>& nums2) {
        unordered_map<int, int> nextGreater;
        stack<int> st;
        vector<int> ans;

        for (int num : nums2) {
            while (!st.empty() && num > st.top()) {
                nextGreater[st.top()] = num;
                st.pop();
            }
            st.push(num);
        }

        while (!st.empty()) {
            nextGreater[st.top()] = -1;
            st.pop();
        }

        for (auto x : nums1) {
            ans.push_back(nextGreater[x]);
        }

        return ans;
    }
};
```