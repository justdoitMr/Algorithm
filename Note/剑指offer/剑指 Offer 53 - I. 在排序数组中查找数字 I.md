## 剑指 Offer 53 - I. 在排序数组中查找数字 I

### [剑指 Offer 53 - I. 在排序数组中查找数字 I](https://leetcode-cn.com/problems/zai-pai-xu-shu-zu-zhong-cha-zhao-shu-zi-lcof/)

### 累加法

~~~ java
class Solution {
    public int search(int[] nums, int target) {

        return search_A(nums,target);

    }

    public int search_A(int[] nums, int target) {

        int right = 0;
        int count = 0;
        while(right < nums.length){
            if(nums[right] == target){
               count++;
            }
            right++;
        }

        return count;

    }
}
~~~

### 二分法

因为是排序数组，所以可以找到左右边界，然后相减即可。

~~~ java
class Solution {
    public int search(int[] nums, int target) {

        return search_A(nums,target);
    }


    // 使用二分法
    public int search_A(int nums[],int target){

        int left = 0;
        int right = nums.length;
        while(left < right){
            int mid =(left+right)/2;
            if(nums[mid] == target){
                // 搜索右侧边界
                right = mid;
            }else if(nums[mid] < target){
                // 增大左侧边界
                left = mid+1;
            }else if(nums[mid] > target){
                // 收缩右侧边界
                right =mid;
            }
        }
        //退出循环，找到左侧边界
        int temp = left;

        // 寻找右侧边界
        left = 0;
        right = nums.length;
        while(left < right){
            int mid = (left+right)/2;
            if(target == nums[mid]){
                // 收缩左侧边界
                left =mid+1;
            }else if(target < nums[mid]){
                // 收缩右侧边界
                right = mid;
            }else if(target > nums[mid]){
                // 收缩左侧边界
                left = mid+1;
            }
        }
        return right - temp;
    }
}
~~~

