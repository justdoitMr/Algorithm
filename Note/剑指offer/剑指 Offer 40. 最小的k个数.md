## 剑指 Offer 40. 最小的k个数

### [剑指 Offer 40. 最小的k个数](https://leetcode-cn.com/problems/zui-xiao-de-kge-shu-lcof/)

### 排序思想

时间复杂度是o(nlogn)

### 快排选择思想

基于39题目思想，一趟快排，可以把第k小数字放到第k个位置，那么找前k个小的数字，返回k之前的全部数据即可。

![1645515217536](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/22/153338-936964.png)

~~~java
class Solution {
    public int[] getLeastNumbers(int[] arr, int k) {
        if (k == 0 || arr.length == 0) {
            return new int[0];
        }
        // 最后一个参数表示我们要找的是下标为k-1的数
        return quickSearch(arr, 0, arr.length - 1, k - 1);
    }

    private int[] quickSearch(int[] nums, int lo, int hi, int k) {
        // 每快排切分1次，找到排序后下标为j的元素，如果j恰好等于k就返回j以及j左边所有的数；
        int j = partition(nums, lo, hi);
        if (j == k) {
            return Arrays.copyOf(nums, j + 1);
        }
        // 否则根据下标j与k的大小关系来决定继续切分左段还是右段。
        return j > k? quickSearch(nums, lo, j - 1, k): quickSearch(nums, j + 1, hi, k);
    }

    // 快排切分，返回下标j，使得比nums[j]小的数都在j的左边，比nums[j]大的数都在j的右边。
    private int partition(int[] nums, int lo, int hi) {
        int v = nums[lo];
        int i = lo, j = hi + 1;
        while (true) {
            while (++i <= hi && nums[i] < v);
            while (--j >= lo && nums[j] > v);
            if (i >= j) {
                break;
            }
            int t = nums[j];
            nums[j] = nums[i];
            nums[i] = t;
        }
        nums[lo] = nums[j];
        nums[j] = v;
        return j;
    }
}
~~~

![1645515269454](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/22/153429-459099.png)

但是这种方法，会修改原来数组的值。

### 时间复杂度为o(nlogk)算法，适合处理海量数据

![1645515319701](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202202/22/153519-15023.png)

~~~ java
public int[] getLeastNumbers_A(int[] arr, int k) {

        // 使用大顶堆维护前k个数字,基于大顶堆
        PriorityQueue<Integer> maxRoot = new PriorityQueue(k,new Comparator<Integer>() {
           @Override
           public int compare(Integer o1, Integer o2) {
            //    默认是小顶堆实现
               return o2-o1;
           }
        });

        // 遍历数组
        for(int i=0;i<arr.length;i++){
            // 首先查看大顶堆是否满了
            if(maxRoot.size() == k){
                // 如果满了，查看大顶堆中是否有当前元素
                //if(!maxRoot.contains(arr[i])){
                    // 如果没有当前元素，就擦好看堆顶元素大小
                    if(maxRoot.peek()>arr[i]){
                        // 删除堆顶元素
                        maxRoot.poll();
                        // 插入当前元素
                        maxRoot.offer(arr[i]);
                    }
              //  }

            }else{
                // 大顶堆不满
                maxRoot.offer(arr[i]);
            }
        }

        // 遍历大顶堆，插入元素
        int res[] =new int[k];
        int index = 0;
        while(!maxRoot.isEmpty()){
            res[index++]=maxRoot.poll();
        }

        return res;
    }
~~~

对于K个数字，插入，删除和查找时间复杂度是logk,那么对于n个元素，遍历一遍时间复杂度是o(n)所以总的时间复杂度是o(nligk)。

需要注意的是，优先队列，默认是小顶堆。

### 冒泡排序

使用冒泡排序，每一次可以找到一个最小的元素，查找k次即可。

所以说，只要一种排序算法，每一次可以选出一个最小的元素，都可以解决这个问题。

## 从海量数据中查基于partition方法找前k个数据思路

|                        | 基于partition方法 | 基于排序树                          |
| ---------------------- | ----------------- | ----------------------------------- |
| 时间复杂度             | o(n)              | 0（nlogk)n是数据总量，k是带查找个数 |
| 是否需要求改原始的数组 | 需要              | 不需要                              |
| 是否适用于海量数据     | 否                | 是                                  |



[两种经典解法详解](https://github.com/justdoitMr/Algorithm/blob/main/Note/Top%20K%20%E9%97%AE%E9%A2%98%E7%9A%84%E4%B8%A4%E7%A7%8D%E7%BB%8F%E5%85%B8%E8%A7%A3%E6%B3%95.md)