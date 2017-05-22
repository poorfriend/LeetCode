## 问题描述
You are playing the following Nim Game with your friend: There is a heap of stones on the table, each time one of you take turns to remove 1 to 3 stones. The one who removes the last stone will be the winner. You will take the first turn to remove the stones.

Both of you are very clever and have optimal strategies for the game. Write a function to determine whether you can win the game given the number of stones in the heap.

For example, if there are 4 stones in the heap, then you will never win the game: no matter 1, 2, or 3 stones you remove, the last stone will always be removed by your friend.


## 分析
如石头的数目不是4的倍数，则第一回合取 n %4，剩下的石头就是4的倍数。地方取1-3中任意一数a，我方则取4-a，最后取得胜利。如果是4的倍数，地方可采取同样的策略。

## 代码

#### 解法一
```cpp
bool canWinNim(int n) {
        return n % 4;
    }
```
