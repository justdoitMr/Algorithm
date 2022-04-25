## [剑指 Offer 56 - I. 数组中数字出现的次数](https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-lcof/)

### 思路

![1650761337150](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/084858-961658.png)

![1650761388483](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/084949-381634.png)

~~~java
public int[] singleNumber(int[] nums) {
    int x = 0;
    for(int num : nums)  // 1. 遍历 nums 执行异或运算
        x ^= num;
    return x;            // 2. 返回出现一次的数字 x
}
~~~

设 nums=[3,3,4,4,1] ，以上计算流程如下图所示。

![1650761426770](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085027-736143.png)

**本题难点：** 数组 numsnumsnums 有 **两个** 只出现一次的数字，因此无法通过异或直接得到这两个数字。

![1650761447989](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085048-161450.png)

![1650761472870](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085113-169794.png)

![1650761487901](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085128-306993.png)

![1650761504742](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085144-412822.png)

~~~java
while(z & m == 0) // m 循环左移一位，直到 z & m ！= 0
    m <<= 1

~~~

![1650761524942](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085206-857102.png)

~~~java
for(int num: nums) {
    if((num & m) != 0) x ^= num;  // 若 num & m != 0 , 划分至子数组 1 ，执行遍历异或
    else y ^= num;                // 若 num & m == 0 , 划分至子数组 2 ，执行遍历异或
}
return new int[] {x, y};          // 遍历异或完毕，返回只出现一次的数字 x 和 y
}
~~~

![1650761551959](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085233-372508.png)

![1650761565570](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085246-645328.png)

![1650761578538](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/24/085259-367890.png)

**完整代码**

~~~java
class Solution {
    public int[] singleNumbers(int[] nums) {
        //因为相同的数字异或为0，任何数字与0异或结果是其本身。
        //所以遍历异或整个数组最后得到的结果就是两个只出现一次的数字异或的结果：即 z = x ^ y
        int z = 0;  
        for(int i : nums) z ^= i;
        //我们根据异或的性质可以知道：z中至少有一位是1，否则x与y就是相等的。
        //我们通过一个辅助变量m来保存z中哪一位为1.（可能有多个位都为1，我们找到最低位的1即可）。
        //举个例子：z = 10 ^ 2 = 1010 ^ 0010 = 1000,第四位为1.
        //我们将m初始化为1，如果（z & m）的结果等于0说明z的最低为是0
        //我们每次将m左移一位然后跟z做与操作，直到结果不为0.
        //此时m应该等于1000，同z一样，第四位为1.
        int m = 1;
        while((z & m) == 0) m <<= 1;
        //我们遍历数组，将每个数跟m进行与操作，结果为0的作为一组，结果不为0的作为一组
        //例如对于数组：[1,2,10,4,1,4,3,3]，我们把每个数字跟1000做与操作，可以分为下面两组：
        //nums1存放结果为0的: [1, 2, 4, 1, 4, 3, 3]
        //nums2存放结果不为0的: [10] (碰巧nums2中只有一个10，如果原数组中的数字再大一些就不会这样了)
        //此时我们发现问题已经退化为数组中有一个数字只出现了一次
        //分别对nums1和nums2遍历异或就能得到我们预期的x和y
        int x = 0, y = 0;
        for(int i : nums) {
            //这里我们是通过if...else将nums分为了两组，一边遍历一遍异或。
            //跟我们创建俩数组nums1和nums2原理是一样的。
            if((i & m) == 0) x ^= i;
            else y ^= i;
        }
        return new int[]{x, y};
    }
}
~~~

- 第一轮整体遍历，求出a^b（因为相同的数字异或为0，0异或任何数字为数字自身）
- 然后结合a^b以及原来数组求出这两个数字 
  - 原理：用一个只有一位为1的数字来遍历异或整个数组，把这个数组分成两个子数组（异或结果相同的数字在同一个子数组），如果是两个相同的数字，它们一定在同一个子数组里（保证子数组异或时为0），现在只需要把两个只出现一次的数字分到不同的子数组，那么子数组分别遍历异或得到的两个数字就是这两个数字。
  - 怎么把两个只出现一次的数字分到不同地子数组？ 
    - 找到a^b第一个为1的位置，异或结果为1说明a和b在这一位上不同，那用只有这一位为1的数字m去分别异或a和b，得到的结果一定不同，也就把a和b分到了不同的子数组。结合上一点得出结果。