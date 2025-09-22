# Problem: Number of Senior Citizens  

**URL:** [Number of Senior Citizens – LeetCode](https://leetcode.com/problems/number-of-senior-citizens/)  
**Statement:** You are given a 0-indexed array of strings `details`. Each element of `details` provides information about a given passenger compressed into a string of length 15.  

- The first ten characters consist of the phone number of passengers.  
- The next character denotes the gender of the person.  
- The following two characters are used to indicate the age of the person.  
- The last two characters determine the seat allotted to that person.  

Return the number of passengers who are strictly more than 60 years old.  

---
### ✅ Solution – String Parsing  
```cpp
class Solution {
public:
    int countSeniors(vector<string>& details) {
        int cnt = 0;

        for (string s : details) {
            char a = s[11];
            char b = s[12];

            int x = a - '0';
            int y = b - '0';

            int num = x * 10 + y;

            if (num > 60)
                cnt++;
        }
        return cnt;
    }
};
``