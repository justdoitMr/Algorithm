## [剑指 Offer 51. 数组中的逆序对](https://leetcode-cn.com/problems/shu-zu-zhong-de-ni-xu-dui-lcof/)

### 回溯法

首先想到的是回溯法，将所有的组合全部计算出来，然后判断是否合法即可计算答案，但是会超出内存限制。

~~~java
class Solution {
    ArrayList<ArrayList<Integer>> res = new ArrayList();
    public int reversePairs(int[] nums) {

        reversePairs_A(nums,new ArrayList(),0);
        return res.size();

    }

// 使用回溯法
    public void reversePairs_A(int nums[],ArrayList<Integer> list,int idx){
        if(list.size() == 2){
            if(list.get(0) > list.get(1)){
                res.add(new ArrayList<Integer>(list));
            }
            return;
        }

        for(int i=idx;i<nums.length;i++){
            list.add(nums[i]);
            reversePairs_A(nums,list,i+1);
            list.remove(list.size()-1);
        }
    }
}
~~~

