# Problem: Unique Email Addresses  

**URL:** [Unique Email Addresses – LeetCode](https://leetcode.com/problems/unique-email-addresses/)  
**Statement:** Every valid email consists of a local name and a domain name, separated by the `'@'` sign. Besides lowercase letters, the email may contain one or more `'.'` or `'+'`.  

- If you add periods `'.'` between some characters in the local name part of an email address, mail sent there will be forwarded to the same address without dots in the local name. This rule does not apply to domain names.  
- If you add a plus `'+'` in the local name, everything after the first plus sign will be ignored. This allows certain emails to be filtered. This rule does not apply to domain names.  
- It is possible to use both of these rules at the same time.  

Given an array of strings `emails` where we send one email to each `emails[i]`, return the number of different addresses that actually receive mails.  

---
### ✅ Solution – String Processing with Set  
```cpp
class Solution {
public:
    int numUniqueEmails(vector<string>& emails) {
        set<string> ans;

        for (int i = 0; i < emails.size(); i++) {
            string s = emails[i];
            int idx = s.find('@');

            string local = s.substr(0, idx);
            string domain = s.substr(idx);

            string temp;
            for (char ch : local) {
                if (ch == '.')
                    continue;
                if (ch != '+') {
                    temp.push_back(ch);
                } else {
                    break;
                }
            }

            ans.insert(temp + domain);
        }

        return ans.size();
    }
};
```