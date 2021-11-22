


## 剑指 Offer 11. 旋转数组的最小数字


### [剑指 Offer 11. 旋转数组的最小数字](https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/)

如下图所示，寻找旋转数组的最小元素即为寻找 **右排序数组** 的首个元素 nums[x] ，称 x*x* 为 **旋转点** 

![1637291563742](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/19/111244-229557.png)

排序数组的查找问题首先考虑使用 **二分法** 解决，其可将 **遍历法** 的 **线性级别** 时间复杂度降低至 **对数级别** 

![1637291603256](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/19/111324-99348.png)

![1637291689163](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/19/111449-763618.png)

![1637291712212](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/19/111512-182806.png)

以上题解出自：[题解](https://leetcode-cn.com/problems/xuan-zhuan-shu-zu-de-zui-xiao-shu-zi-lcof/solution/mian-shi-ti-11-xuan-zhuan-shu-zu-de-zui-xiao-shu-3/)

**完整代码**

~~~ java
class Solution {
   public int minArray(int[] numbers) {

        return minArray_A(numbers);

    }

    public int minArray_A(int[] numbers) {

       int i = 0, j = numbers.length - 1;
        while (i < j) {
            int m = (i + j) / 2;
            if (numbers[m] > numbers[j]) i = m + 1;
            else if (numbers[m] < numbers[j]) j = m;
            else j--;
        }
        return numbers[i];
    }
}
~~~



