
4<!-- TOC -->

- [剑指 Offer 61. 扑克牌中的顺子](#剑指-offer-61-扑克牌中的顺子)
  - [剑指 Offer 61. 扑克牌中的顺子](#剑指-offer-61-扑克牌中的顺子-1)
  - [HashMap法](#hashmap法)
    - [完整代码](#完整代码)

<!-- /TOC -->

## 剑指 Offer 61. 扑克牌中的顺子

### [剑指 Offer 61. 扑克牌中的顺子](https://leetcode-cn.com/problems/bu-ke-pai-zhong-de-shun-zi-lcof/)

### HashMap法

首先对数组中的元素统计，使用HashMap,，分别统计灭一个元素的个数，在统计的过程中，记录最小值。

我们假设顺子都是从小到大，也就是从扑克牌中从最小值连续开始的顺子。

然后从最小值开始累加，这一步主要是判断是不是连续的顺子，如果没有当前元素，就看有咩有大小王，也就是0元素，有的话就可以代替，如果没有就就返回false；

#### 完整代码

~~~ java
class Solution {
    public boolean isStraight(int[] nums) {

        return isStraight_A(nums);
    }

  public boolean isStraight_A(int[] nums) {

        int sz = nums.length;

        if(sz == 0){
            return true;
        }
        // 首先统计各个数字出现的次数
        HashMap<Integer,Integer> map = new HashMap();
        int min=Integer.MAX_VALUE;
        for(int i=0;i<sz;i++){
            
            if(min > nums[i] && nums[i] != 0){
                min = nums[i];
            }
            if(map.containsKey(nums[i])){
                map.put(nums[i],map.get(nums[i])+1);
            }else{
                map.put(nums[i],1);
            }
        }
        int i=0;
        while(i<5){
            if(!map.containsKey(min)){
                if(map.containsKey(0)&&map.get(0)> 0){
                    map.put(0,map.get(0)-1);
                    min++;
                    i++;
                    continue;
                }else{
                    return false;
                }
            }
            i++;
            min++;
        }
        return true;

    }
}
~~~

