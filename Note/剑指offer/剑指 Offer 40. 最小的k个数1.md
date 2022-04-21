## [剑指 Offer 40. 最小的k个数](https://leetcode-cn.com/problems/zui-xiao-de-kge-shu-lcof/)

注意找前 K 大/前 K 小问题不需要对整个数组进行 O(NlogN)O(NlogN)O(NlogN) 的排序！
例如本题，直接通过快排切分排好第 K 小的数（下标为 K-1），那么它左边的数就是比它小的另外 K-1 个数啦

### 用快排最最最高效解决 TopK 问题：O(N)

~~~java
class Solution {
    public int[] getLeastNumbers(int[] arr, int k) {

        if(k <=0){
            return new int[0];
        }

        int num=quickSelect(arr,k);
        int res[] = new int[k];
        int i=0;
        while(i<k){
            res[i]=arr[i];
            i++;
        }
        return res;

    }

    public int quickSelect(int []arr,int k){

        int sz = arr.length;
        // 注意这里的下表问题，因为从0开始，所以找到k-1个即可
        int target =k-1;
        int left = 0;
        int right = sz-1;
        while(true){
            int partitionIdx = partition(arr,left,right);
            if(partitionIdx == target){
                return arr[partitionIdx];
            }else if(target < partitionIdx){
                right = partitionIdx-1;
            }else{
                left = partitionIdx+1;
            }
        }
    }

    public int partition(int []arr,int left,int right){
                //以当前数组的最后一个元素作为中枢pivot，进行划分
        int pivot = arr[left];
       while (left < right){
           while (left < right&&arr[right]>= pivot){
               right--;
           }
           arr[left]=arr[right];
           while (left < right && pivot>=arr[left]){
               left++;
           }
           arr[right]=arr[left];
       }
       arr[left]=pivot;
       return left;
    }
}
~~~

> 注意找最小k个数和最大k个数的区别：
>
> 最小k个数，因为数组下表从0开始，所以找到k-1个即可。
>
> 如果是找最大k个数，那么我们数组一般是从小到大排序，所以找到sz-k个即可。

![1650521163556](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202204/21/140604-536183.png)

### 大根堆(前 K 小) / 小根堆（前 K 大),Java中有现成的 PriorityQueue，实现起来最简单：O(NlogK)

~~~java
// 保持堆的大小为K，然后遍历数组中的数字，遍历的时候做如下判断：
// 1. 若目前堆的大小小于K，将当前数字放入堆中。
// 2. 否则判断当前数字与大根堆堆顶元素的大小关系，如果当前数字比大根堆堆顶还大，这个数就直接跳过；
//    反之如果当前数字比大根堆堆顶小，先poll掉堆顶，再将该数字放入堆中。
class Solution {
    public int[] getLeastNumbers(int[] arr, int k) {
        if (k == 0 || arr.length == 0) {
            return new int[0];
        }
        // 默认是小根堆，实现大根堆需要重写一下比较器。
        Queue<Integer> pq = new PriorityQueue<>((v1, v2) -> v2 - v1);
        for (int num: arr) {
            if (pq.size() < k) {
                pq.offer(num);
            } else if (num < pq.peek()) {
                pq.poll();
                pq.offer(num);
            }
        }
        
        // 返回堆中的元素
        int[] res = new int[pq.size()];
        int idx = 0;
        for(int num: pq) {
            res[idx++] = num;
        }
        return res;
    }
}
~~~

### 二叉搜索树也可以 O(NlogK)O(NlogK)O(NlogK)解决 TopK 问题哦

BST 相对于前两种方法没那么常见，但是也很简单，和大根堆的思路差不多～
要提的是，与前两种方法相比，BST 有一个好处是求得的前K大的数字是有序的。

因为有重复的数字，所以用的是 TreeMap 而不是 TreeSet（有的语言的标准库自带 TreeMultiset，也是可以的）。

TreeMap的key 是数字，value 是该数字的个数。
我们遍历数组中的数字，维护一个数字总个数为 K 的 TreeMap：

1. 若目前 map 中数字个数小于 K，则将 map 中当前数字对应的个数 +1；
2. 否则，判断当前数字与 map 中最大的数字的大小关系：若当前数字大于等于 map 中的最大数字，就直接跳过该数字；若当前数字小于 map 中的最大数字，则将 map 中当前数字对应的个数 +1，并将 map 中最大数字对应的个数减 1。

~~~java
class Solution {
    public int[] getLeastNumbers(int[] arr, int k) {
        if (k == 0 || arr.length == 0) {
            return new int[0];
        }
        // TreeMap的key是数字, value是该数字的个数。
        // cnt表示当前map总共存了多少个数字。
        TreeMap<Integer, Integer> map = new TreeMap<>();
        int cnt = 0;
        for (int num: arr) {
            // 1. 遍历数组，若当前map中的数字个数小于k，则map中当前数字对应个数+1
            if (cnt < k) {
                map.put(num, map.getOrDefault(num, 0) + 1);
                cnt++;
                continue;
            } 
            // 2. 否则，取出map中最大的Key（即最大的数字), 判断当前数字与map中最大数字的大小关系：
            //    若当前数字比map中最大的数字还大，就直接忽略；
            //    若当前数字比map中最大的数字小，则将当前数字加入map中，并将map中的最大数字的个数-1。
            Map.Entry<Integer, Integer> entry = map.lastEntry();
            if (entry.getKey() > num) {
                map.put(num, map.getOrDefault(num, 0) + 1);
                if (entry.getValue() == 1) {
                    map.pollLastEntry();	
                } else {
                    map.put(entry.getKey(), entry.getValue() - 1);
                }
            }
            
        }

        // 最后返回map中的元素
        int[] res = new int[k];
        int idx = 0;
        for (Map.Entry<Integer, Integer> entry: map.entrySet()) {
            int freq = entry.getValue();
            while (freq-- > 0) {
                res[idx++] = entry.getKey();
            }
        }
        return res;
    }
}

~~~

### 关于TreeMap一些方法的使用

~~~java
//        默认是从小到达排序
        TreeMap<Integer, Integer> map = new TreeMap<Integer, Integer>();
//        判断是否包含某一个key
        map.containsKey(1);
//        获取第一个key
        map.firstKey();
//        获取最后一个key
        map.lastKey();
//        删除某一个键值对
        map.remove(1);
//      获取第一个键值对
        Map.Entry<Integer, Integer> integerIntegerEntry = map.firstEntry();
//         获取最后一个键值对
        Map.Entry<Integer, Integer> integerIntegerEntry1 = map.lastEntry();
//        删除第一个键值对
        map.pollFirstEntry();
//        删除最后一个键值对
        map.pollLastEntry();
~~~

