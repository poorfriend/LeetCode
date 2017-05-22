## 问题描述
Given an array of 2n integers, your task is to group these integers into n pairs of integer, say (a1, b1), (a2, b2), ..., (an, bn) which makes sum of min(ai, bi) for all i from 1 to n as large as possible.

Example 1:

Input: [1,4,3,2]

Output: 4

Explanation: n is 2, and the maximum sum of pairs is 4.

Note:

- n is a positive integer, which is in the range of [1, 10000].
- All the integers in the array will be in the range of [-10000, 10000].

## 分析
假设最大值b和第二大值d不在同一组，这两个二元组分别为(a, b), (c,d),若这两个二元组的最小值和为a +c < (d + min(a , c)), 也就是说b,d该在同一组，依次递推

## 代码

#### 解法一
```cpp
int arrayPairSum(vector<int>& nums) {
        int res =0 ;
        sort(nums.begin(), nums.end());
        for(int i=0; i <nums.size(); i = i+2)
            res += nums[i];
        return res;
    }
```
#### 解法二
```cpp
int arrayPairSum(vector<int>& nums) {
        int ret = 0;
        bool flag = true;
        array<int, 20001> hashtable{ 0 };
        for (const auto n : nums) {
            ++hashtable[n + 10000];
        }
        for (int i = 0; i < 20001;) {
            if (hashtable[i] > 0) {
                if (flag) {
                    flag = false;
                    ret += (i - 10000);
                    --hashtable[i];
                } else  {
                    flag = true;
                    --hashtable[i];
                }
            } else
                ++i;
        }
        return ret;
    }
```