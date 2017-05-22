## 问题描述
Given a string, you need to reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

Example 1:
```
Input: "Let's take LeetCode contest"
Output: "s'teL ekat edoCteeL tsetnoc"
```
Note:
- In the string, each word is separated by single space and there will not be any extra space in the string.

## 分析


## 代码

```cpp
vector<vector<int>> matrixReshape(vector<vector<int>>& nums, int r, int c) {
        int total = nums.size() * nums[0].size();
        if (r * c != total)
            return nums;
        vector<vector<int>> tmp(r, vector<int>(c,0));
        int ncount=0;
        for(const auto v : nums)
            for(const auto i :v){
                tmp[ncount / c][ncount % c] = i;
                ++ncount;
            }
        return tmp;
```



```cpp
    string reverseWords(string s) {
        istringstream tmp(s);
        string str, res, ts;
        while(tmp >> str)
        {
            for(auto i=0;i<str.size();i++)
                ts[str.size()- 1 - i] = str[i];
            res += ts + ' ';
        }
        return res.substr(0, res.size()-1);
```