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
string reverseWords(string s) {
    if(s.empty())
        return s;
    int loc = -1;
    string res(s.size(), 'a');
    for(string::size_type i=0; i < s.size(); ++i){
        if(s[i] != ' '){
            if( i < s.size()-1)
                continue;
            ++i;
        }
        for(string::size_type j=loc+1; j<i; ++j){
            res[j] = s[i - j + loc]; 
        }
        if(i < s.size()-1)
            res[i] = ' ';
        loc = i;
    }
    return res;    
}
```

```cpp
string reverseWords(string s) {
    size_t front = 0;
    for(int i = 0; i <= s.length(); ++i){
        if(i == s.length() || s[i] == ' '){
            reverse(&s[front], &s[i]);
            front = i + 1;
        }
    }
    
    return s;
}
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