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

~~~ java
class Solution {
    public int search(int[] nums, int target) {

 
        return search_B(nums,target);

    }

     public int search_B(int[] nums, int target) {

         if(nums.length == 0){
             return 0;
         }
        //  寻找左侧边界
        int left = 0;
        int right =nums.length;
        while(left < right){
            int mid=left+(right-left)/2;
            if(nums[mid] == target){
                right = mid;
            }else if(nums[mid] < target){
                left =mid+1;
            }else if(nums[mid]> target){
                right = mid;
            }
        }
        int temp = left;
        // 搜索右侧边界

         left = 0;
         right =nums.length;
        while(left < right){
            int mid=left+(right-left)/2;
            if(nums[mid] == target){
                left = mid+1;
            }else if(nums[mid] < target){
                left =mid+1;
            }else if(nums[mid]> target){
                right = mid;
           }
        }
        return left-temp;
     }
    }
}
~~~

