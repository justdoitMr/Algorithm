
<!-- TOC -->

- [剑指 Offer 12. 矩阵中的路径](#剑指-offer-12-矩阵中的路径)
  - [剑指 Offer 12. 矩阵中的路径](#剑指-offer-12-矩阵中的路径-1)
  - [思路](#思路)

<!-- /TOC -->

## 剑指 Offer 12. 矩阵中的路径

### [剑指 Offer 12. 矩阵中的路径](https://leetcode-cn.com/problems/ju-zhen-zhong-de-lu-jing-lcof/)

### 思路

**首先考虑递归的出口有哪几种情况**

1. 考虑到搜索边界，也就是每一次递归判断i(控制board横坐标的索引)，j(控制board数组列索引)是否合法，这是第一个条件。
2. 第二个条件是判断当前字符(`board[i][j]`)是否和`ch[index]`字符一样，一样的话继续递归，不一样就返回。
3. 第三个条件是判断当前访问的`board[i][j]`字符在当此遍历中是否访问过，访问过就返回false。

上面三个递归出口条件，遇到任何一个就可以返回false。

**考虑回溯退出条件**

如果在二维数组中找到字符串就退出，`index`是控制字符串的索引，所以当index等于字符串长度-1的时候，说明找到，这个是回溯的出口。

**考虑递归体**

每次从一个字符开始查找，我们都要从其周围四个方向依次回溯查找。

**总体思路**

- 使用二维布尔数组记录之前的位置是否已经被访问过，如果已经被访问过的话，则在 dfs 的过程中，直接 return false 即可。也就是说，此路已经不通了；
- 如果当前遍历到的字符不等于` board[i][j] `位置上的字符，那么说明此路也是不通的，因此返回 false；
- 至于递归结束的条件：如果指针 start 能够来到 word 的最后一个字符，那么说明能够在矩阵 board 中找到一条路径，此时返回 true；
- 在遍历到当前` board[i][j] `的时候，首先应将该位置的 `visited[i][j] `设置为 true，表明访问过；
- 然后，递归地去 `board[i][j] `的上下左右四个方向去找，剩下的路径；
- 在 dfs 的过程当中，如果某条路已经不通了，那么那么需要回溯，也就是将 `visited[i][j] `位置的布尔值重新赋值为 fasle；
- 最后，返回 ans 即可。

**完整代码**

~~~ java
class Solution {
    public boolean exist(char[][] board, String word) {

        if(word.length() == 0 || board.length == 0){
            return false;
        }

        int rowlen=board.length;
        int collen=board[0].length;
        int visit[][]=new int[rowlen][collen];

        char []ch = word.toCharArray();
        for(int i=0;i< rowlen;i++){
            Arrays.fill(visit[i],0);
        }

        for(int i=0;i< rowlen;i++){
            for(int j=0;j< collen;j++){
                // 每一次都从ch数组0位置开始找
                if(exist_A(board,ch,i,j,visit,0)){
                    return true;
                }
            }
        }

        return false;

    }

     public boolean exist_A(char[][] board, char[] word,int i,int j,int [][]visit,int index) {

        if(i< 0 || i>=board.length || j<0||j>=board[0].length||word[index] != board[i][j] ||visit[i][j] != 0){
            return false;
        }
        // 找到返回true
         if(index == word.length-1){
             return true;
         }
         visit[i][j] = 1;
         boolean ans= false;

         ans=exist_A(board,word,i-1,j,visit,index+1)||exist_A(board,word,i+1,j,visit,index+1)
         || exist_A(board,word,i,j-1,visit,index+1)||exist_A(board, word, i, j+1, visit, index+1);
        //  回溯
        visit[i][j]=0;
        return ans;

    }
}
~~~

**时间复杂度分析**

![1639532201302](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202112/15/093642-48791.png)

