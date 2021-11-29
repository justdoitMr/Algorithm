## 剑指 Offer 47. 礼物的最大价值

### [剑指 Offer 47. 礼物的最大价值](https://leetcode-cn.com/problems/li-wu-de-zui-da-jie-zhi-lcof/)

### 动态规划

首先说明dp数组的含义，`dp[i][j]`表示到`dp[i][j]`为止，所能获得的最大价值

那么我们如何才能到达i,j的为止呢？有两种方法，一种是从i-1,j到达，一种是从i,j-1到达，显然，这两种走法，哪一种获得的价值大，我们就采用哪一种，所以可以得到状态转移方程：

~~~ java
dp[i][j]=Math.max(dp[i][j],Math.max(grid[i-1][j-1]+dp[i-1][j],grid[i-1][j-1]+dp[i][j-1]));
~~~

### 完整代码

~~~ java
class Solution {
    public int maxValue(int[][] grid) {

        return maxValue_A(grid);

    }

    public int maxValue_A(int[][] grid) {

        int row = grid.length;
        int col = grid[0].length;
        if(row == 0){
            return -1;
        }
        // 声明一个dp数组，表示到dp[i,j]为止，所能获得的最大价值
        int [][]dp=new int[row+1][col+1];
        // 初始化操作，第0行和第0列都是0
        for(int i=0;i<row;i++){
            Arrays.fill(dp[i],0);
        }

        for(int i=1;i<=row;i++){
            for(int j=1;j<=col;j++){
                dp[i][j]=Math.max(dp[i][j],Math.max(grid[i-1][j-1]+dp[i-1][j],grid[i-1][j-1]+dp[i][j-1]));
            }
        }

        return dp[row][col];

    }
}
~~~

时间复杂度是o(n^2).

空间复杂度是o(n^2)，但是空间复杂度可以进行优化操作，因为我们的状态之和前一行有关，所以空间复杂度可以优化位o(col)。