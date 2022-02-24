## 剑指 Offer 56 - I. 数组中数字出现的次数

### [剑指 Offer 56 - I. 数组中数字出现的次数](https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-lcof/)

### 异或的性质

![1645680116763](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/24/132157-637464.png)

### [136. 只出现一次的数字](https://leetcode-cn.com/problems/single-number/)

~~~java
class Solution {
    public int singleNumber(int[] nums) {

        return singleNumber_A(nums);
    }

    // 使用异或运算
    public int singleNumber_A(int []nums){

        int res = 0;
        for(int num:nums){
            res =res ^ num;
        }
        return res;
    }
}
~~~

![1645680535429](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/24/132856-381966.png)

### 137.只出现一次的数字 II

#### [137. 只出现一次的数字 II](https://leetcode-cn.com/problems/single-number-ii/)

![1645681442565](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/24/134403-472470.png)

**完整代码**

~~~java
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int res = 0;
        for (int i = 0; i < 32; i++) { // 因为nums[i]是32位整数，
        // 所以针对每一位的对应二进制数值求和
            int sum = 0;
            for (int num : nums) {
                sum += ((num >> i) & 1); // 提取从右往左数第i位的数值，将所有nums[i]
                // 二进制下的第i位数值进行求和
            }
            if (sum % 3 == 1) { // 如果没办法被3整除，那么说明落单的那个数的第i位是1不是0
                res |= (1 << i);
            }
        }
        return res; // 输出结果
    }
};
~~~

### [剑指 Offer 56 - I. 数组中数字出现的次数](https://leetcode-cn.com/problems/shu-zu-zhong-shu-zi-chu-xian-de-ci-shu-lcof/)

![1645681809377](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/24/135010-139669.png)

**完整代码**

~~~java
class Solution {
public:
    vector<int> singleNumber(vector<int>& nums) {
        int group1 = 0, group2 = 0;
        int diff = 0, bit = 1;
        for (int num : nums) // 异或运算，目的是找到两个落单数值的不同，便于后面分类
            diff ^= num;
        while ((diff & bit) == 0) //  左移运算，找到二者某一位的不同，将这一位定为分类依据
            bit <<= 1;
        for (int num : nums) { // 对元素进行遍历    
            if(num & bit) group1 ^= num; // 对于num，如果对于bit为1，分类为group1，对这个
            // group进行异或，可以找到落单的数值
            else group2 ^= num; // 如果num的bit对应的是0，那么异或找到另一个落单的数值
        }
        return vector<int> {group1, group2};   // 返回结果
    }
};
~~~

