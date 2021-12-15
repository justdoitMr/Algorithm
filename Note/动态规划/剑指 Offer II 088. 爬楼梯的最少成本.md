## 剑指 Offer II 088. 爬楼梯的最少成本

### [剑指 Offer II 088. 爬楼梯的最少成本](https://leetcode-cn.com/problems/GzCJIP/)

### 动态规划

这一道题目和动态规划问题很像，我们先假设当前在低i个楼梯的位置，那么我们有几种办法到第i个楼梯，有可能从i-1位置，也有可能是从i-2的位置，那么具体是从i-1位置还是从i-2位置呢？

根据题目描述，哪一个付出的代价小，我们就从哪一个，所以从这里我们的dp数组代表的含义和状态转移方程就确定下来了：

- dp数组表示当第i个位置的时候，付出的最小代价。
- 状态转移方程：
  - `dp[i]=dp[i-1],dp[i-2]+cost[i]`。
- dp数组的初始化：
  - 根据题目说明，当i=0或者1的时候，那么付出的代价就是cost[0]，costp[1]。
- 确定遍历顺序
  - 本题目中dp数组是一个一维数组，所以需要自底向上进行遍历，根据状态转移方程推出结果。

本题目中，严格按照做动态规划问题的思路和步骤，给出答案。

**完整代码**

~~~ java
class Solution {
    public int minCostClimbingStairs(int[] cost) {

        return minCostClimbingStairs_A(cost);

    }

    public int minCostClimbingStairs_A(int[] cost) {

        if(cost.length <0){
            return 0;
        }

        int []dp = new int[cost.length];

        // 初始化操作
        dp[0]=cost[0];
        dp[1]=cost[1];
        for(int i=2;i<cost.length;i++){
            dp[i]=Math.min(dp[i-1],dp[i-2])+cost[i];
        }

        return Math.min(dp[cost.length-1],dp[cost.length-2]);
    }
}
~~~

- 时间复杂度：o(n)

- 空间复杂度：o(n)

本题目中，对空间复杂度还可以进行优化，我们发现当前状态dp[i]只和前两个状态有关，所以我们可以使用两个变量，保存前两个状态，这样空间复杂度就是o(1)。

