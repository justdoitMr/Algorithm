## 剑指 Offer 42. 连续子数组的最大和

### [剑指 Offer 42. 连续子数组的最大和](https://leetcode-cn.com/problems/lian-xu-zi-shu-zu-de-zui-da-he-lcof/)

> `dp[i]`表示到第i个元素为止，最大的连续和是dp[i]

~~~java
class Solution {
    public int maxSubArray(int[] nums) {

        return maxSubArray_A(nums);
    }

    public int maxSubArray_A(int nums[]){
        int sz = nums.length;

        if(sz == 0){
            return 0;
        }
        if(sz==1){
            return nums[0];
        }
        // 定义dp数组
        int []dp =new int[sz+1];
        // 初始化dp数组
        dp[0]=nums[0];
        int res = nums[0];
        for(int i=1;i<sz;i++){
            dp[i]=Math.max(dp[i-1]+nums[i],nums[i]);
            res = Math.max(res,dp[i]);
        }
        return res;
    }
}
~~~

