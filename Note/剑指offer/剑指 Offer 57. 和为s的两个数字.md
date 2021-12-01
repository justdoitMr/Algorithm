
<!-- TOC -->

- [剑指 Offer 57. 和为s的两个数字](#剑指-offer-57-和为s的两个数字)
  - [剑指 Offer 57. 和为s的两个数字](#剑指-offer-57-和为s的两个数字-1)
  - [双指针](#双指针)

<!-- /TOC -->

## 剑指 Offer 57. 和为s的两个数字

### [剑指 Offer 57. 和为s的两个数字](https://leetcode-cn.com/problems/he-wei-sde-liang-ge-shu-zi-lcof/)

### 双指针

~~~ java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        return twoSum_A(nums,target);

    }

    public int[] twoSum_A(int[] nums, int target) {

        int res [] = new int[2];

        if(nums.length == 0){
            return res;
        }
        int left=0;
        int right = nums.length-1;
        while(left <= right){
            int sum = nums[left]+nums[right];
            if(sum < target){
                left++;
            }else if(sum > target){
                right--;
            }else{
                res[0]=nums[left];
                res[1]=nums[right];
                break;
            }
        }

        return res;
    }
}
~~~

只需要遍历一遍数组即可，所以时间复杂度是o(n)