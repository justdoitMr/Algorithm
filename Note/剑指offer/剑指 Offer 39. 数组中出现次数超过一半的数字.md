## 剑指 Offer 39. 数组中出现次数超过一半的数字

### [剑指 Offer 39. 数组中出现次数超过一半的数字](https://leetcode-cn.com/problems/shu-zu-zhong-chu-xian-ci-shu-chao-guo-yi-ban-de-shu-zi-lcof/)

### 使用摩尔投票法

**完整代码**

~~~ java
public int majorityElement_A(int[] nums) {

         int votes=0;
         int x=nums[0];
         for(int num : nums){
             
             if(votes == 0){
                 x = num;
                 votes+=1;
             }else{
                 if(num == x){
                     votes+=1;
                 }else{
                    votes -=1;
                 }
                 
             }
         }
         return x;
    }
~~~

只需要遍历一遍数组即可，所以时间复杂度是o(n)，空间复杂度是o(1)。

### 使用HashMap统计

**完整代码**

~~~ java
public int majorityElement_B(int[] nums) {

        if(nums.length == 1){
            return nums[0];
        }

        Map<Integer,Integer> hash = new HashMap();
        int sz=nums.length/2;
        for(int num:nums){
            if(hash.containsKey(num)){
                hash.put(num,hash.get(num)+1);
                if(hash.get(num)>sz){
                    return num;
                }
            }else{
                hash.put(num,1);
            }
        }

        return -1;


    }
~~~

