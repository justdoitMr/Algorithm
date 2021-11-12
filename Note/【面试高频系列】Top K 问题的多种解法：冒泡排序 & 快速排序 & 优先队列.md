## 【面试高频系列】Top K 问题的多种解法：冒泡排序 & 快速排序 & 优先队列 ...

## 题目描述

这是 LeetCode 上的**「703. 数据流中的第 K 大元素」**，难度为 **「Easy」**。

设计一个找到数据流中第 k 大元素的类（class）。

注意是排序后的第 k 大元素，不是第 k 个不同的元素。

请实现 KthLargest 类：

- KthLargest(int k, int[] nums) 使用整数 k 和整数流 nums 初始化对象。
- int add(int val) 将 val 插入数据流 nums 后，返回当前数据流中第 k 大的元素。

示例：

```
输入：
["KthLargest", "add", "add", "add", "add", "add"]
[[3, [4, 5, 8, 2]], [3], [5], [10], [9], [4]]

输出：
[null, 4, 5, 5, 8, 8]

解释：
KthLargest kthLargest = new KthLargest(3, [4, 5, 8, 2]);
kthLargest.add(3);   // return 4
kthLargest.add(5);   // return 5
kthLargest.add(10);  // return 5
kthLargest.add(9);   // return 8
kthLargest.add(4);   // return 8
```

提示：

- 1 <= k <=
- 0 <= nums.length <=
-  <= nums[i] <=
-  <= val <=
- 最多调用 add 方法  次
- 题目数据保证，在查找第 k 大元素时，数组中至少有 k 个元素

## 冒泡排序解法（TLE）

每次调用 `add` 时先将数装入数组，然后遍历 `k` 次，通过找 `k` 次最大值来找到 Top K。

代码：

```
class KthLargest {
    int k;
    List<Integer> list = new ArrayList<>(10009);
    public KthLargest(int _k, int[] _nums) {
        k = _k;
        for (int i : _nums) list.add(i);
    }
    public int add(int val) {
        list.add(val);
        int cur = 0;
        for (int i = 0; i < k; i++) {
            int idx = findMax(cur, list.size() - 1);
            swap(cur++, idx);
        }
        return list.get(cur - 1); 
    }
    int findMax(int start, int end) {
        int ans = 0, max = Integer.MIN_VALUE;
        for (int i = start; i <= end; i++) {
            int t = list.get(i);
            if (t > max) {
                max = t;
                ans = i;
            }
        }
        return ans;
    }
    void swap(int a, int b) {
        int c = list.get(a);
        list.set(a, list.get(b));
        list.set(b, c);
    }
}
```

- 时间复杂度：
- 空间复杂度：

## 快速排序解法

上述的解法时间复杂度是  的，当 `k` 很大的时候会超时。

我们可以使用快排来代替冒泡。

将复杂度变为 ，不能说  复杂度一定比  要低，但  通常更加接近 。

本题的 `n` 的范围是 ， 解法的效率等于一个常数为 15 以内的  算法：

代码：

```
class KthLargest {
    int k;
    List<Integer> list = new ArrayList<>(10009);
    public KthLargest(int _k, int[] _nums) {
        k = _k;
        for (int i : _nums) list.add(i);
    }
    
    public int add(int val) {
        list.add(val);
        Collections.sort(list);
        return list.get(list.size() - k);
    }
}
```

- 时间复杂度：
- 空间复杂度：

**PS. `Collections.sort` 内部最终会调用 `Arrays.sort` 进行排序。而 `Arrays.sort()` 本身不只有「双轴快排」一种实现，在排序数量少的情况下会直接使用「冒泡排序」，这里的分析是假定了 `Collections.sort` 最终使用的是 `Arrays.sort` 的「双轴快排」。**

## 优先队列解法

使用优先队列构建一个容量为 `k` 的小根堆。

将 `nums` 中的前 `k` 项放入优先队列（此时堆顶元素为前 `k` 项的最大值）。

随后逐项加入优先队列：

- 堆内元素个数达到 `k` 个：

- - 加入项小于等于堆顶元素：加入项排在第 `k` 大元素的后面。直接忽略
  - 加入项大于堆顶元素：将堆顶元素弹出，加入项加入优先队列，调整堆

- 堆内元素个数不足 `k` 个，将加入项加入优先队列

将堆顶元素进行返回（数据保证返回答案时，堆内必然有 `k` 个元素）。

代码：

```
class KthLargest {
    int k;
    PriorityQueue<Integer> queue;
    public KthLargest(int _k, int[] _nums) {
        k = _k;
        queue = new PriorityQueue<>(k, (a,b)->Integer.compare(a,b));
        int n = _nums.length;
        for (int i = 0; i < k && i < n; i++) queue.add(_nums[i]);
        for (int i = k; i < n; i++) add(_nums[i]);
    }
    public int add(int val) {
        int t = !queue.isEmpty() ? queue.peek() : Integer.MIN_VALUE;
        if (val > t || queue.size() < k) {
            if (!queue.isEmpty() && queue.size() >= k) {
                queue.poll();
            }
            queue.add(val);
        }
        return queue.peek();
    }
}
```

- 时间复杂度：最坏情况下，`n` 个元素入堆，都触发堆调整。复杂度为
- 空间复杂度：

