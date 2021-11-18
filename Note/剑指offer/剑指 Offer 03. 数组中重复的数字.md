## 剑指 Offer 03. 数组中重复的数字

### [剑指 Offer 03. 数组中重复的数字](https://leetcode-cn.com/problems/shu-zu-zhong-zhong-fu-de-shu-zi-lcof/)

### 使用HashMap

很容易想到的一种方法是对数组进行遍历一遍，然后把元素添加到HashMap中：

- key是数组中的元素，value是元素出现的次数
- 当HashMap中含有某一个key的时候，说明此元素已经重复，返回即可。

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

