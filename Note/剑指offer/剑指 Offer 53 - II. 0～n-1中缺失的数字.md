## 剑指 Offer 53 - II. 0～n-1中缺失的数字

### [剑指 Offer 53 - II. 0～n-1中缺失的数字](https://leetcode-cn.com/problems/que-shi-de-shu-zi-lcof/)

### 原数组比较法

在原始数组上操作：

1. 如果当前位置上的元素只等于等闲数组下表，不做任何操作。
2. 如果当前位置元素只不等于等钱位置下表，那么就把当前元素放到属于他的位置，也就是下表位他的元素值的位置。
3. 再次判断当前位置的元素值，如果不等于下表值，一直循环直到等于下表值为止

#### 完整代码

~~~ java
class Solution {
    public int missingNumber(int[] nums) {

        return missingNumber_A(nums);
    }

    public int missingNumber_A(int[] nums) {

        if(nums.length == 0){
            return -1;
        }
        for(int i=0;i<nums.length;i++){
            while(nums[i] != i && nums[i] != -1){
                if(nums[i] < nums.length ){
                    int temp = nums[nums[i]];
                    nums[nums[i]]=nums[i];
                    nums[i]=temp;
                }else{
                    nums[i] = -1;
                }
                
            }
        }

        for(int i=0;i<nums.length;i++){
            if(nums[i] == -1){
                return i;
            }
        }

        return nums.length;
    }
}
~~~

遍历一遍数组即可，所以时间复杂度是o(n)

### 二分法

1. 数组nums具有二段性：在缺失的数字之前，必然有nums[i]==i，在缺失的数字之后，必然有nums[i]!=i
2. 因此，只需要二分找出第一个nums[i]!=i，此时下标i就是答案
3. 若数组元素中没有找到此下标，那么缺失的就是n

**题解**

![1638234860645](C:\Users\MrR\AppData\Roaming\Typora\typora-user-images\1638234860645.png)

图片来自leetcode:

#### 完整代码

~~~ java
class Solution {
    public int missingNumber(int[] nums) {
        int i = 0, j = nums.length - 1;
        while(i <= j) {
            int m = (i + j) / 2;
            if(nums[m] == m) i = m + 1;
            else j = m - 1;
        }
        return i;
    }
}
~~~

时间复杂度是o(logn)