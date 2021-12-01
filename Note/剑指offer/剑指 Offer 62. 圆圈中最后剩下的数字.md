
<!-- TOC -->

- [剑指 Offer 62. 圆圈中最后剩下的数字](#剑指-offer-62-圆圈中最后剩下的数字)
  - [剑指 Offer 62. 圆圈中最后剩下的数字](#剑指-offer-62-圆圈中最后剩下的数字-1)

<!-- /TOC -->

## 剑指 Offer 62. 圆圈中最后剩下的数字

### [剑指 Offer 62. 圆圈中最后剩下的数字](https://leetcode-cn.com/problems/yuan-quan-zhong-zui-hou-sheng-xia-de-shu-zi-lcof/)

本题目实际是约瑟夫环问题，参考下面给出的解释：

![1638325483080](C:\Users\MrR\AppData\Roaming\Typora\typora-user-images\1638325483080.png)

图片来自官方网站。

这个题解也比较容易理解：[题解](https://leetcode-cn.com/problems/yuan-quan-zhong-zui-hou-sheng-xia-de-shu-zi-lcof/solution/tai-jiao-bi-ye-ye-neng-dong-dong-tai-gui-zmwj/)

**完整代码**

~~~ java
class Solution {
    public int lastRemaining(int n, int m) {

        return lastRemaining_A(n,m);

    }

    public int lastRemaining_A(int n, int m) { 

        int x = 0;
        for (int i = 2; i <= n; i++) {
            x = (x + m) % i;
        }
        return x;
    }
}
~~~

时间复杂度：o(n)