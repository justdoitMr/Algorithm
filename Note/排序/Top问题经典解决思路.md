
<!-- TOC -->

- [Top问题](#top问题)
- [**堆**](#堆)
- [快速排序变形](#快速排序变形)
- [两种方法比较](#两种方法比较)

<!-- /TOC -->

## Top问题

Top K 问题有两种不同的解法，一种解法使用堆（优先队列），另一种解法使用类似快速排序的分治法。这两种方法各有优劣，最好都掌握。本文用图解的形式讲解这道问题的两种解法，包括三个部分：

- 方法一：堆，时间复杂度
- 方法二：快排变形，（平均）时间复杂度
- 两种方法的优劣比较

## **堆**  

比较直观的想法是使用堆数据结构来辅助得到最小的 k 个数。堆的性质是每次可以找出最大或最小的元素。我们可以使用一个大小为 k 的最大堆（大顶堆），将数组中的元素依次入堆，当堆的大小超过 k 时，便将多出的元素从堆顶弹出。

这样，**由于每次从堆顶弹出的数都是堆中最大的，最小的 k 个元素一定会留在堆里**。这样，把数组中的元素全部入堆之后，堆中剩下的 k 个元素就是最大的 k 个数了。

Java 中的 `PriorityQueue`。在面试中，我们不需要实现堆的内部结构，把数据结构使用好，会分析其复杂度即可。

~~~ java
public int[] getLeastNumbers(int[] arr, int k) {
    if (k == 0) {
        return new int[0];
    }
    // 使用一个最大堆（大顶堆）
    // Java 的 PriorityQueue 默认是小顶堆，添加 comparator 参数使其变成最大堆
    Queue<Integer> heap = new PriorityQueue<>(k, (i1, i2) -> Integer.compare(i2, i1));

    for (int e : arr) {
        // 当前数字小于堆顶元素才会入堆
        if (heap.isEmpty() || heap.size() < k || e < heap.peek()) {
            heap.offer(e);
        }
        if (heap.size() > k) {
            heap.poll(); // 删除堆顶最大元素
        }
    }

    // 将堆中的元素存入数组
    int[] res = new int[heap.size()];
    int j = 0;
    for (int e : heap) {
        res[j++] = e;
    }
    return res;
}
~~~

![1638068059319](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/28/105419-106054.png)

## 快速排序变形

Top K 问题的另一个解法就比较难想到，需要在平时有算法的积累。实际上，“查找第 k 大的元素”是一类算法问题，称为**选择问题**。找第 k 大的数，或者找前 k 大的数，有一个经典的 quick select（快速选择）算法。这个名字和 quick sort（快速排序）看起来很像，算法的思想也和快速排序类似，都是分治法的思想。

让我们回顾快速排序的思路。快速排序中有一步很重要的操作是 partition（划分），从数组中随机选取一个枢纽元素 v，然后原地移动数组中的元素，使得比 v 小的元素在 v 的左边，比 v 大的元素在 v 的右边，如下图所示：

![1638068144385](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/28/105544-900456.png)

![1638068177192](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/28/105618-454902.png)

~~~ java
    /**
     * quickSort 每次选择一个元素并且将整个数组以这个元素分为两部分，小于该元素的放右边，大于该元素的放左边
     * @param arr
     * @param k
     * @return
     */
    public static int quickSort(int[] arr,int k){

        //第k大元素，即排序后下标为n-k的元素，使用partition方法确定下标n-k元素
        int target = arr.length-k;
        int from =0;
        int to = arr.length-1;
//        快速选择算法主题部分
        while (true){
            //partition就是划分操作，将arr划分成满足条件的两个子表
            int partitionIndex = partition(arr,from,to);
            if(target == partitionIndex){
                return arr[partitionIndex];
            }else if(partitionIndex < target){
                from = partitionIndex+1;
            }else {
               to = partitionIndex-1;
            }
        }


    }

    public static int partition(int[] arr,int left,int right){
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
~~~

![1638068226068](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/28/105707-366800.png)

## 两种方法比较

在面试中，另一个常常问的问题就是这两种方法有何优劣。看起来分治法的快速选择算法的时间、空间复杂度都优于使用堆的方法，但是要注意到快速选择算法的几点局限性：

第一，算法需要修改原数组，如果原数组不能修改的话，还需要拷贝一份数组，空间复杂度就上去了。

第二，算法需要保存所有的数据。如果把数据看成输入流的话，使用堆的方法是来一个处理一个，不需要保存数据，只需要保存 k 个元素的最大堆。而快速选择的方法需要先保存下来所有的数据，再运行算法。当数据量非常大的时候，甚至内存都放不下的时候，就麻烦了。

所以当数据量大的时候还是用基于堆的方法比较好。