## [剑指 Offer 15. 二进制中1的个数](https://leetcode-cn.com/problems/er-jin-zhi-zhong-1de-ge-shu-lcof/)

### 方法一：逐位判断

- 根据 **与运算** 定义，设二进制数字 n ，则有：
  - 若 n & 1 = 0，则 n二进制 **最右一位** 为 0
  - 若 n & 1 = 1，则 n 二进制 **最右一位** 为 1
- 根据以上特点，考虑以下 循环判断 ：
  - 判断 n最右一位是否为 1 ，根据结果计数。
  - 将 n右移一位（本题要求把数字 nn看作无符号数，因此使用 无符号右移 操作）。

**算法流程**

1. 初始化数量统计变量 res = 0
2. 循环逐位判断： 当 n = 0时跳出。
   1. res += n & 1 ： 若 n & 1 = 1 ，则统计数 res加一。
   2. n >>= 1 ： 将二进制数字 n 无符号右移一位（ Java 中无符号右移为 ">>>" ） 。
3. 返回统计数量 res 。

![1645419861138](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/21/130421-145983.png)

**完整代码**

~~~java
    public int hammingWeight_A(int n){

        int res = 0;
        while(n !=0){
            res +=n&1;
            n>>>=1;
        }
        return res;
    }
~~~

![1645420155238](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/21/130916-843551.png)