## 剑指 Offer 21. 调整数组顺序使奇数位于偶数前面

### [剑指 Offer 21. 调整数组顺序使奇数位于偶数前面](https://leetcode-cn.com/problems/diao-zheng-shu-zu-shun-xu-shi-qi-shu-wei-yu-ou-shu-qian-mian-lcof/)

使用双指针你发，先从前往后遍历找到一个偶数，然后在从后往前找到一个技术，交换两个元素即可。

**完整代码**

~~~java
class Solution {
    public int[] exchange(int[] nums) {

        return exchange_A(nums);

    }

    // 使用双指针
    public int[] exchange_A(int[] nums) {

        if(nums == null){
            return nums;
        }
        int left = 0;
        int right = nums.length-1;

        while(left < right){
            while(nums[left]%2 != 0 && left < right){
                left++;
            }
            // 跳出内循环，说明找到偶数
            while(nums[right]%2 == 0&& left < right){
                right --;
            }
            // 跳出循环，说明找到计数
            // 交换元素
            int temp = nums[right];
            nums[right]=nums[left];
            nums[left]=temp;

            right --;
            left ++;
        }

        return nums;

    }
}
~~~

虽然有双层循环，但是时间复杂度是o(1)，整体事件复杂度是o(n)；

考虑程序的可扩展性，我们可以写一个函数判断是奇数或者是偶数，然后针对不同的要求，只需要修改一小部分代码就行，提高了程序的可扩展性。