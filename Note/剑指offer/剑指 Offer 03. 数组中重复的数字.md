## 剑指 Offer 03. 数组中重复的数字

### [剑指 Offer 03. 数组中重复的数字](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

### 使用HashMap

很容易想到的一种方法是对数组进行遍历一遍，然后把元素添加到HashMap中：

- key是数组中的元素，value是元素出现的次数
- 当HashMap中含有某一个key的时候，说明此元素已经重复，返回即可。判断哈希表中是否有某一个key的时间复杂度是o(1)。所以总的时间复杂度是o(n)。

**完整代码**

~~~ java
class Solution {
    public int findRepeatNumber(int[] nums) {


        return findRepeatNumber_A(nums);
    }

    //简单的方式是使用一个HashMap
     public int findRepeatNumber_A(int[] nums) {

         Map<Integer,Integer> hashMap=new HashMap();

         for(int i=0;i< nums.length;i++){
             if(hashMap.containsKey(nums[i])){
                 return nums[i];
             }else{
                 hashMap.put(nums[i],1);
             }
        }
        return -1;
     }
}
~~~

这种方法需要遍历一遍数组，所以时间复杂度是o(n)，需要使用额外的空间o(n)。

### 使用排序

第二种想法是使用排序，在排好序的数组中找到一个重复的元素，相对来说环是比较容易，但是时间复杂度是o(nlogn)。

### o(N)时间复杂度算法

借用HashMap的话，时间复杂度是o(N),空间复杂度也是o(n)。

那么有没有一种空间复杂度是o(1)的算法呢？

考虑到题目，数组中元素都在0-n-1的范围内，所以我们可以在原数组中进行操作:

1. 依次遍历数组中的每一个元素，查看当前元素值是否和元素的下表相等。
2. 如果相等，进入下一次循环
3. 如果不相等，就把当前元素m放到数组下表为m的位置，相当于交换位置，这里需要注意一下，交换完成之后，当前位置的元素值和其下表还可能不一样，所以需要接着交换，也就是这里需要使用一个while循环判断。

**完整代码**

~~~ java
public int findRepeatNumber_B(int[] nums) {

        for(int i=0;i<nums.length;i++){
            // 判断元素值和下表值是否一样
            while(nums[i] != i){
                // nums[i]位置的元素不等于i
                if(nums[nums[i]] != nums[i]){
                    int temp=nums[nums[i]];
                    nums[nums[i]]=nums[i];
                    nums[i]=temp;
                }else{
                    return nums[i];
                }
                
            }
        }
        return -1;
    }
~~~

代码需要遍历整个数组，所以时间复杂度是0(n),但是所有的操作都在原数组空间上操作，不需要额外的数据空间。

尽管有两层循环，但是内层循环做多遍历两次就可以找到重复的元素，所以总的时间复杂度是o(n)。