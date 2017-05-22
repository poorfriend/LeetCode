## 问题描述
You are given a map in form of a two-dimensional integer grid where 1 represents land and 0 represents water. Grid cells are connected horizontally/vertically (not diagonally). The grid is completely surrounded by water, and there is exactly one island (i.e., one or more connected land cells). The island doesn't have "lakes" (water inside that isn't connected to the water around the island). One cell is a square with side length 1. The grid is rectangular, width and height don't exceed 100. Determine the perimeter of the island.

Example 1:

[[0,1,0,0],
 [1,1,1,0],
 [0,1,0,0],
 [1,1,0,0]]

Answer: 16

Explanation: The perimeter is the 16 yellow stripes in the image below:


![test](https://leetcode.com/static/images/problemset/island.png)


## 分析
每个正方形4条边，相邻的正方形减少两条边，共有n-1个相邻正方形，所以最后还有4*n-2(n-1) = 2n+2

## 代码

#### 解法一
```cpp
int islandPerimeter(vector<vector<int>>& grid) {
        int res;
        for(int i=0; i <grid.size();i++){
            for(int j=0; j<grid[i].size(); j++){
                if (grid[i][j] == 1)
                    ++res;
            }
        }
        return res * 2 + 2;
    }
```
