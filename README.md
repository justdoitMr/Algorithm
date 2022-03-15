# Algorithm

### 仓库介绍

leetcode 题解，记录自己的 leetcode 解题之路。

本仓库目前分为**四个**部分：

- 第一个部分是 算法刷题技巧和一些算法模板，掌握一些接替模板，可以快速帮助我们理解一个问题的接替方法。
- 第二部分是对于数据结构与算法的总结
- 第三部分是对刷过的提机型汇总。
- 第四部分是计划， 这里会记录将来要加入到以上三个部分内容

### 算法基础

1. 时间复杂度
2. 空间复杂度

### 基础数据结构

#### 线性表

- 线性表
- 列表（必学）
- 链表（必学）
- 跳跃表（知道原理理，应⽤用，最后⾃自⼰己实现⼀一遍）
- 并查集（建议结合刷题学习）

> 不⽤用说，链表、列列表必须，不不过重点是链表。

#### 栈与队列

- 栈（必学）
- 队列（必学）
- 优先队列、堆（必学）
- 多级反馈队列（原理理与应⽤用）

> 特别是优先队列，再刷题的时候，还是经常⽤用到的，队列列与栈，是最基本的数据结构，必学。可以通过博客来学习

#### 哈希表（必学）

- 碰撞解决⽅方法：开放定址法、链地址法、再次哈希法、建⽴立公共溢出区（必学）
- 布隆隆过滤器器（原理理与应用）

#### 树

- 二叉树：各种遍历（递归与⾮递归）（必学）
- 哈夫曼树与编码（原理理与应用）
- AVL树（必学）
- B 树与 B+ 树（原理理与应用）
- 前缀树（原理理与应用）
- 红⿊黑树（原理理与应用）
- 线段树（原理理与应用）
- 堆：最大堆 ／ 最小堆
- 树与图：最近公共祖先、并查集
- 字符串：前缀树（字典树） ／ 后缀树

> 树相关是知识还是挺多的，建议看书，可以看《算法第四版》。

#### 数组

- 矩阵（必学）

### 算法概述

#### 十大排序算法

- 简单排序：插入排序、选择排序、冒泡排序（必学）
- 分治排序：快速排序、归并排序（必学，快速排序还要关注中轴的选取⽅方式）
- 分配排序：桶排序、基数排序
- 树状排序：堆排序（必学）
- 其他：计数排序（必学）、希尔排序

#### 图论算法

- 图的表示：邻接矩阵和邻接表
- 遍历算法：深度搜索和⼴广度搜索(必学)
- 最短路路径算法：Floyd，Dijkstra（必学）
- 最小⽣生成树算法：Prim，Kruskal（必学）
- 实际常⽤用算法：关键路路径、拓扑排序（原理与应用）
- ⼆分图匹配：配对、匈⽛牙利利算法（原理与应用）
- 拓展：中心性算法、社区发现算法（原理与应用）

#### 搜索算法

- 回溯算法
- 递归算法
- 深度优先遍历(DFS)
- 广度优先遍历(BFS)
- 二叉搜索树

#### 动态规划

- 树形DP：01背包问题
- 线性DP：最长公共子序列列、最长公共⼦子串
- 区间DP：矩阵最大值（和以及积）
- 数位DP：数字游戏
- 状态压缩DP：旅行商

#### 字符匹配算法

- 正则表达式
- 模式匹配：KMP、Boyer-Moore

#### 其他算法技巧

- 双指针
- 二分查找
- 滑动窗口
- 分治算法
- 贪心算法
- 前缀匹配树


---

在这一部分，我将会更新一些常用的算法技巧，掌握一些算法技巧不是偷懒，而是为了更好的刷题，更高效的去解答每一道题目，可以帮助我们迅速的去定位一些问题的解法，常用的一些技巧，比如：双指针，二分查找，滑动窗口，递归等等，并且还会借鉴网上的一些模板，形成自己的一套接替思路，希望可以帮到大家。

> 注：本人在学习算法阶段，笔记是参考博主`labuladong`,还是非常感谢这位大神的方法和技巧，让我受益匪浅，下面的笔记是参考这位博主的，加了一些自己的观点和代码补充。

---

### 排序算法

[排序算法介绍](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E6%8E%92%E5%BA%8F%E7%AE%97%E6%B3%95%E4%BB%8B%E7%BB%8D.md)

#### 基于交换的排序

1. [冒泡排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F.md)
2. [快速排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F.md)

### 基于堆排序和快速选择排序的top算法比较

1. [两种算法比较](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/Top%E9%97%AE%E9%A2%98%E7%BB%8F%E5%85%B8%E8%A7%A3%E5%86%B3%E6%80%9D%E8%B7%AF.md)
2. [Top K问题解决方法](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/Top%20K%E9%97%AE%E9%A2%98%E8%A7%A3%E5%86%B3%E6%96%B9%E6%A1%88.md)

#### 基于插入的排序

1. [插入排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E6%8F%92%E5%85%A5%E6%8E%92%E5%BA%8F.md)
2. [希尔排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E5%B8%8C%E5%B0%94%E6%8E%92%E5%BA%8F.md)

#### 基于选择的排序

1. [简单选择排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E7%AE%80%E5%8D%95%E9%80%89%E6%8B%A9%E6%8E%92%E5%BA%8F.md)
2. [堆排序](https://www.cnblogs.com/chengxiao/p/6129630.html)
3. [堆排序代码](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E5%A0%86%E6%8E%92%E5%BA%8F%E4%BB%A3%E7%A0%81.md)

[归并排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E5%BD%92%E5%B9%B6%E6%8E%92%E5%BA%8F.md)

[基数排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8E%92%E5%BA%8F/%E5%9F%BA%E6%95%B0%E6%8E%92%E5%BA%8F.md)


### 剑指Offer

#### 数据结构

涉及数组，字符串，链表，树，栈和队列等数据结构，这一部分主要是熟悉java语言中的各种集合的实现和方法，理解每一种数据结构的优点和缺点，使用情景等。

##### 数组

数组：使用连续的内存，可以根据下表在o(1)时间内读取和写入任何元素，效率很高，但是在插入一个元素的时候，效率就很低。数组可以用来实现哈希表，把数组的下表作为哈希表的键值key，而元素就代表哈希表的值。

3. [剑指 Offer 03. 数组中重复的数字](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2003.%20%E6%95%B0%E7%BB%84%E4%B8%AD%E9%87%8D%E5%A4%8D%E7%9A%84%E6%95%B0%E5%AD%97.md)
4. [剑指 Offer 04. 二维数组中的查找](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2004.%20%E4%BA%8C%E7%BB%B4%E6%95%B0%E7%BB%84%E4%B8%AD%E7%9A%84%E6%9F%A5%E6%89%BE%5D.md)
5. [剑指 Offer 05. 替换空格](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2005.%20%E6%9B%BF%E6%8D%A2%E7%A9%BA%E6%A0%BC.md)
6. [剑指 Offer 06. 从尾到头打印链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2006.%20%E4%BB%8E%E5%B0%BE%E5%88%B0%E5%A4%B4%E6%89%93%E5%8D%B0%E9%93%BE%E8%A1%A8.md)
7. [剑指 Offer 07. 重建二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2007.%20%E9%87%8D%E5%BB%BA%E4%BA%8C%E5%8F%89%E6%A0%91.md)
8. [剑指offer面试题8：二叉树的下一个节点](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87offer%E9%9D%A2%E8%AF%95%E9%A2%988%EF%BC%9A%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E4%B8%8B%E4%B8%80%E4%B8%AA%E8%8A%82%E7%82%B9.md)
9. [剑指 Offer 09. 用两个栈实现队列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2009.%20%E7%94%A8%E4%B8%A4%E4%B8%AA%E6%A0%88%E5%AE%9E%E7%8E%B0%E9%98%9F%E5%88%97.md)

#### 算法

##### 递归和循环

如果我们在程序中需要重复的多次计算相同的问题，那么通常可以使用**递归**或者**循环**，但是往往递归算法的效率不如循环。

7. [剑指 Offer 10- I. 斐波那契数列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92%E6%A1%86%E6%9E%B6.md)
8. [剑指 Offer 10- II. 青蛙跳台阶问题](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2010-%20II.%20%E9%9D%92%E8%9B%99%E8%B7%B3%E5%8F%B0%E9%98%B6%E9%97%AE%E9%A2%98.md)

##### 查找和排序

- **顺序查找**：元素无序时查找
- **二分查找**：相对有序的数组中查找
- **哈希查找**：o(1)时间内查找元素
- **二叉排序树**：一种特殊的树结构

9. [剑指 Offer 11. 旋转数组的最小数字](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2011.%20%E6%97%8B%E8%BD%AC%E6%95%B0%E7%BB%84%E7%9A%84%E6%9C%80%E5%B0%8F%E6%95%B0%E5%AD%97.md)

#### 回溯

10. [剑指 Offer 12. 矩阵中的路径](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2012.%20%E7%9F%A9%E9%98%B5%E4%B8%AD%E7%9A%84%E8%B7%AF%E5%BE%84.md)

#### 动态规划

11. [剑指 Offer 14- I. 剪绳子](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2014-%20I.%20%E5%89%AA%E7%BB%B3%E5%AD%90.md)

#### 位运算
12. [剑指 Offer 15. 二进制中1的个数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E4%BD%8D%E8%BF%90%E7%AE%97.md)
13. [二进制中一的个数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2015.%20%E4%BA%8C%E8%BF%9B%E5%88%B6%E4%B8%AD1%E7%9A%84%E4%B8%AA%E6%95%B0.mds)

#### 代码的完整性

13. [高质量代码](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E9%AB%98%E8%B4%A8%E9%87%8F%E4%BB%A3%E7%A0%81.md)
14. [剑指 Offer 16. 数值的整数次方](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2016.%20%E6%95%B0%E5%80%BC%E7%9A%84%E6%95%B4%E6%95%B0%E6%AC%A1%E6%96%B9.md)
15. [剑指 Offer 17. 打印从1到最大的n位数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2017.%20%E6%89%93%E5%8D%B0%E4%BB%8E1%E5%88%B0%E6%9C%80%E5%A4%A7%E7%9A%84n%E4%BD%8D%E6%95%B0.md)
16. [剑指 Offer 18. 删除链表的节点](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2018.%20%E5%88%A0%E9%99%A4%E9%93%BE%E8%A1%A8%E7%9A%84%E8%8A%82%E7%82%B9.md)
17. [剑指 Offer 21. 调整数组顺序使奇数位于偶数前面](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2021.%20%E8%B0%83%E6%95%B4%E6%95%B0%E7%BB%84%E9%A1%BA%E5%BA%8F%E4%BD%BF%E5%A5%87%E6%95%B0%E4%BD%8D%E4%BA%8E%E5%81%B6%E6%95%B0%E5%89%8D%E9%9D%A2.md)

#### 代码的鲁棒性(健壮性)

健壮性就是需要我们考虑不合法的输入，针对不合法的输入需要给出反馈，比如空指针，空字符串，索引越界怎么办。

18. [剑指 Offer 22. 链表中倒数第k个节点](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E9%93%BE%E8%A1%A8.md)
19. [剑指 Offer 23. 链表中环的入口节点](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E9%93%BE%E8%A1%A8.md)
20. [剑指 Offer 24. 反转链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E9%93%BE%E8%A1%A8.md)
21. [剑指 Offer 25. 合并两个排序的链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E9%93%BE%E8%A1%A8.md)
22. [剑指 Offer 26. 树的子结构](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2026.%20%E6%A0%91%E7%9A%84%E5%AD%90%E7%BB%93%E6%9E%84.md)
23. [剑指 Offer 27. 二叉树的镜像](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2027.%20%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E9%95%9C%E5%83%8F.md)
24. [剑指 Offer 28. 对称的二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2028.%20%E5%AF%B9%E7%A7%B0%E7%9A%84%E4%BA%8C%E5%8F%89%E6%A0%91.md)
25. [剑指 Offer 30. 包含min函数的栈](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2030.%20%E5%8C%85%E5%90%ABmin%E5%87%BD%E6%95%B0%E7%9A%84%E6%A0%88.md)
26. [剑指 Offer 31. 栈的压入、弹出序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2031.%20%E6%A0%88%E7%9A%84%E5%8E%8B%E5%85%A5%E3%80%81%E5%BC%B9%E5%87%BA%E5%BA%8F%E5%88%97.md)
27. [剑指 Offer 32 - I. 从上到下打印二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2032%20-%20I.%20%E4%BB%8E%E4%B8%8A%E5%88%B0%E4%B8%8B%E6%89%93%E5%8D%B0%E4%BA%8C%E5%8F%89%E6%A0%91.md)
28. [剑指 Offer 32 - II. 从上到下打印二叉树 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2032%20-%20II.%20%E4%BB%8E%E4%B8%8A%E5%88%B0%E4%B8%8B%E6%89%93%E5%8D%B0%E4%BA%8C%E5%8F%89%E6%A0%91%20II.md)
29. [剑指 Offer 32 - III. 从上到下打印二叉树 III](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2032%20-%20III.%20%E4%BB%8E%E4%B8%8A%E5%88%B0%E4%B8%8B%E6%89%93%E5%8D%B0%E4%BA%8C%E5%8F%89%E6%A0%91%20III.md)
30. [剑指 Offer 33. 二叉搜索树的后序遍历序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2033.%20%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E7%9A%84%E5%90%8E%E5%BA%8F%E9%81%8D%E5%8E%86%E5%BA%8F%E5%88%97.md)
31. [剑指 Offer 34. 二叉树中和为某一值的路径](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2034.%20%E4%BA%8C%E5%8F%89%E6%A0%91%E4%B8%AD%E5%92%8C%E4%B8%BA%E6%9F%90%E4%B8%80%E5%80%BC%E7%9A%84%E8%B7%AF%E5%BE%84.md)
32. [剑指 Offer 35. 复杂链表的复制](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2035.%20%E5%A4%8D%E6%9D%82%E9%93%BE%E8%A1%A8%E7%9A%84%E5%A4%8D%E5%88%B6.md)
33. [剑指 Offer 36. 二叉搜索树与双向链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2036.%20%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E4%B8%8E%E5%8F%8C%E5%90%91%E9%93%BE%E8%A1%A8.md)
34. [剑指 Offer 38. 字符串的排列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2038.%20%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%9A%84%E6%8E%92%E5%88%97.md)
35. [剑指 Offer 39. 数组中出现次数超过一半的数字](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2039.%20%E6%95%B0%E7%BB%84%E4%B8%AD%E5%87%BA%E7%8E%B0%E6%AC%A1%E6%95%B0%E8%B6%85%E8%BF%87%E4%B8%80%E5%8D%8A%E7%9A%84%E6%95%B0%E5%AD%97.md)
36. [剑指 Offer 40. 最小的k个数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2040.%20%E6%9C%80%E5%B0%8F%E7%9A%84k%E4%B8%AA%E6%95%B0.md)
37. [Top问题解决方案](https://github.com/justdoitMr/Algorithm/blob/main/Note/Top%E9%97%AE%E9%A2%98%E7%BB%8F%E5%85%B8%E8%A7%A3%E5%86%B3%E6%80%9D%E8%B7%AF.md)
38. [剑指 Offer 42. 连续子数组的最大和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2042.%20%E8%BF%9E%E7%BB%AD%E5%AD%90%E6%95%B0%E7%BB%84%E7%9A%84%E6%9C%80%E5%A4%A7%E5%92%8C.md)
39. [剑指 Offer 45. 把数组排成最小的数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2045.%20%E6%8A%8A%E6%95%B0%E7%BB%84%E6%8E%92%E6%88%90%E6%9C%80%E5%B0%8F%E7%9A%84%E6%95%B0.md)
40. [剑指 Offer 46. 把数字翻译成字符串](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2046.%20%E6%8A%8A%E6%95%B0%E5%AD%97%E7%BF%BB%E8%AF%91%E6%88%90%E5%AD%97%E7%AC%A6%E4%B8%B2.md)
41. [剑指 Offer 47. 礼物的最大价值](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2047.%20%E7%A4%BC%E7%89%A9%E7%9A%84%E6%9C%80%E5%A4%A7%E4%BB%B7%E5%80%BC.md)
42. [剑指 Offer 48. 最长不含重复字符的子字符串](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2048.%20%E6%9C%80%E9%95%BF%E4%B8%8D%E5%90%AB%E9%87%8D%E5%A4%8D%E5%AD%97%E7%AC%A6%E7%9A%84%E5%AD%90%E5%AD%97%E7%AC%A6%E4%B8%B2.md)
43. [剑指 Offer 49. 丑数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2049.%20%E4%B8%91%E6%95%B0.md)
44. [剑指 Offer 50. 第一个只出现一次的字符](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2050.%20%E7%AC%AC%E4%B8%80%E4%B8%AA%E5%8F%AA%E5%87%BA%E7%8E%B0%E4%B8%80%E6%AC%A1%E7%9A%84%E5%AD%97%E7%AC%A6.md)
45. [剑指 Offer 53 - I. 在排序数组中查找数字 I](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2053%20-%20I.%20%E5%9C%A8%E6%8E%92%E5%BA%8F%E6%95%B0%E7%BB%84%E4%B8%AD%E6%9F%A5%E6%89%BE%E6%95%B0%E5%AD%97%20I.md)
46. [剑指 Offer 53 - II. 0～n-1中缺失的数字](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2053%20-%20II.%200%EF%BD%9En-1%E4%B8%AD%E7%BC%BA%E5%A4%B1%E7%9A%84%E6%95%B0%E5%AD%97.md)
47. [剑指 Offer 54. 二叉搜索树的第k大节点](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2054.%20%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E7%9A%84%E7%AC%ACk%E5%A4%A7%E8%8A%82%E7%82%B9.md)
48. [剑指 Offer 55 - I. 二叉树的深度]()
49. [剑指 Offer 55 - II. 平衡二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2055%20-%20II.%20%E5%B9%B3%E8%A1%A1%E4%BA%8C%E5%8F%89%E6%A0%91.md)
50. [剑指 Offer 56 - I. 数组中数字出现的次数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2056%20-%20I.%20%E6%95%B0%E7%BB%84%E4%B8%AD%E6%95%B0%E5%AD%97%E5%87%BA%E7%8E%B0%E7%9A%84%E6%AC%A1%E6%95%B0.md)
51. [剑指 Offer 57. 和为s的两个数字](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2057.%20%E5%92%8C%E4%B8%BAs%E7%9A%84%E4%B8%A4%E4%B8%AA%E6%95%B0%E5%AD%97.md)
52. [剑指 Offer 57 - II. 和为s的连续正数序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2057.%20%E5%92%8C%E4%B8%BAs%E7%9A%84%E4%B8%A4%E4%B8%AA%E6%95%B0%E5%AD%97.md)
53. [剑指 Offer 58 - I. 翻转单词顺序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2058%20-%20I.%20%E7%BF%BB%E8%BD%AC%E5%8D%95%E8%AF%8D%E9%A1%BA%E5%BA%8F.md)
54. [剑指 Offer 58 - II. 左旋转字符串](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2058%20-%20II.%20%E5%B7%A6%E6%97%8B%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2.md)
55. [剑指 Offer 59 - I. 滑动窗口的最大值]()
56. [剑指 Offer 59 - II. 队列的最大值](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2059%20-%20II.%20%E9%98%9F%E5%88%97%E7%9A%84%E6%9C%80%E5%A4%A7%E5%80%BC.md)
57. [剑指 Offer 61. 扑克牌中的顺子](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2061.%20%E6%89%91%E5%85%8B%E7%89%8C%E4%B8%AD%E7%9A%84%E9%A1%BA%E5%AD%90.md)
58. [剑指 Offer 62. 圆圈中最后剩下的数字](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2062.%20%E5%9C%86%E5%9C%88%E4%B8%AD%E6%9C%80%E5%90%8E%E5%89%A9%E4%B8%8B%E7%9A%84%E6%95%B0%E5%AD%97.md)

---

### Leetcode hot 100

1. [判断链表是否包含环](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E5%88%A4%E6%96%AD%E9%93%BE%E8%A1%A8%E6%98%AF%E5%90%A6%E5%8C%85%E5%90%AB%E7%8E%AF.md)
2. [两数相加](https://github.com/justdoitMr/Algorithm/blob/main/Note/hot100/2.%20%E4%B8%A4%E6%95%B0%E7%9B%B8%E5%8A%A0.md)
3. [无重复字符的最长子串]()
4. [最长回文子串]()

### 数据结构

---

#### 二叉树

1. [二叉树(一)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91(%E4%B8%80).md)
2. [二叉树(二)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%EF%BC%88%E4%BA%8C%EF%BC%89.md)
3. [二叉树(三)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%EF%BC%88%E4%B8%89%EF%BC%89.md)
4. [二叉树的层次遍历](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E5%B1%82%E6%AC%A1%E9%81%8D%E5%8E%86.md)
5. [二叉树的层平均值](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E5%B1%82%E5%B9%B3%E5%9D%87%E5%80%BC(Easy).md)
6. [N叉树的层次遍历](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/N%E5%8F%89%E6%A0%91%E7%9A%84%E5%B1%82%E6%AC%A1%E9%81%8D%E5%8E%86%EF%BC%88Medium%EF%BC%89.md)
7. [二叉树非递归遍历](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E9%9D%9E%E9%80%92%E5%BD%92%E6%96%B9%E5%BC%8F%E9%81%8D%E5%8E%86.md)
8. [404、二叉树左叶子之和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/404%E3%80%81%E5%B7%A6%E5%8F%B6%E5%AD%90%E4%B9%8B%E5%92%8C.md)
9. [513、找树左下角的值](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/513%E3%80%81%E6%89%BE%E6%A0%91%E5%B7%A6%E4%B8%8B%E8%A7%92%E7%9A%84%E5%80%BC.md)
10. [112、路径总和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/112%E3%80%81%E8%B7%AF%E5%BE%84%E6%80%BB%E5%92%8C1.md)
11. [617、合并二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/617%E3%80%81%E5%90%88%E5%B9%B6%E4%BA%8C%E5%8F%89%E6%A0%91.md)
12. [700、二叉搜索树中的搜索](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/700%E3%80%81%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E4%B8%AD%E7%9A%84%E6%90%9C%E7%B4%A2.md)
13. [297、二叉树的序列化](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E5%BA%8F%E5%88%97%E5%8C%96.md)
14. [二叉搜索树(一)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%B8%80%EF%BC%89.md)
15. [二叉搜索树(二)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%BA%8C%EF%BC%89.md)
16. [二叉搜索树(三)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%B8%89%EF%BC%89.md)


##### 基础算法


##### BFS

1. [BFS(一)](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/BFS(%E4%B8%80).md)
2. [BFS(二)](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/BFS%EF%BC%88%E4%BA%8C%EF%BC%89.md)
3. [BFS和DFS](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/DFS%E5%92%8CBFS.md)
4. [判断有向图中是否有环](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/%E5%88%A4%E6%96%AD%E6%9C%89%E5%90%91%E5%9B%BE%E6%98%AF%E5%90%A6%E5%AD%98%E5%9C%A8%E7%8E%AF.md)
5. [199、二叉树的右视图](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E5%8F%B3%E8%A7%86%E5%9B%BE.md)
6. [116、填充每个节点的下一个右侧节点指针](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%A1%AB%E5%85%85%E6%AF%8F%E4%B8%AA%E8%8A%82%E7%82%B9%E7%9A%84%E4%B8%8B%E4%B8%80%E4%B8%AA%E5%8F%B3%E4%BE%A7%E8%8A%82%E7%82%B9%E6%8C%87%E9%92%88(Medium).md)
7. [找每一层中的最大值](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/%E6%89%BE%E6%AF%8F%E4%B8%80%E5%B1%82%E4%B8%AD%E7%9A%84%E6%9C%80%E5%A4%A7%E5%80%BC(Medium).md)
8. [N叉树的层次遍历](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/N%E5%8F%89%E6%A0%91%E7%9A%84%E5%B1%82%E6%AC%A1%E9%81%8D%E5%8E%86%EF%BC%88Medium%EF%BC%89.md)

##### DFS

1. [剑指 Offer 28. 对称的二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%AF%B9%E7%A7%B0%E4%BA%8C%E5%8F%89%E6%A0%91(Easy).md)
2. [104. 二叉树的最大深度](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E6%B7%B1%E5%BA%A6(Easy).md)
3. [**257. 二叉树的所有路径**](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E6%89%80%E6%9C%89%E8%B7%AF%E5%BE%84.md)
4. [**236. 二叉树的最近公共祖先**](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E6%9C%80%E8%BF%91%E5%85%AC%E5%85%B1%E7%A5%96%E5%85%88.md)
5. [226. 翻转二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%8F%8D%E8%BD%AC%E4%BA%8C%E5%8F%89%E6%A0%91.md8)
6. [222、完全二叉树节点个数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%AE%8C%E5%85%A8%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E8%8A%82%E7%82%B9%E4%B8%AA%E6%95%B0.md)
7. [判断是否是平衡二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%88%A4%E6%96%AD%E6%98%AF%E5%90%A6%E6%98%AF%E5%B9%B3%E8%A1%A1%E4%BA%8C%E5%8F%89%E6%A0%91.md)
8. [**最大键值和**](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E6%9C%80%E5%A4%A7%E9%94%AE%E5%80%BC%E5%92%8C.md)
9. [530、二叉搜索树的最小绝对差.md](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/530%E3%80%81%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E7%9A%84%E6%9C%80%E5%B0%8F%E7%BB%9D%E5%AF%B9%E5%B7%AE.md)
10. [701、二叉搜索树中的插入](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/701%E3%80%81%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E4%B8%AD%E7%9A%84%E6%8F%92%E5%85%A5.md)
11. [450、二叉搜索树中的删除](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/450%E3%80%81%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E4%B8%AD%E7%9A%84%E5%88%A0%E9%99%A4.md)
12. [108.将有序数组转换为二叉搜索树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/108%E3%80%81%E5%B0%86%E6%9C%89%E5%BA%8F%E6%95%B0%E7%BB%84%E8%BD%AC%E6%8D%A2%E4%B8%BA%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91.md)




---

#### 链表

1. [判断链表是否包含环](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E5%88%A4%E6%96%AD%E9%93%BE%E8%A1%A8%E6%98%AF%E5%90%A6%E5%8C%85%E5%90%AB%E7%8E%AF.md)
2. [递归反转整个链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E9%80%92%E5%BD%92%E5%8F%8D%E8%BD%AC%E6%95%B4%E4%B8%AA%E9%93%BE%E8%A1%A8.md)
3. [148. 排序链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/148.%20%E6%8E%92%E5%BA%8F%E9%93%BE%E8%A1%A8.md)
4. [链表相交](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E9%93%BE%E8%A1%A8%E7%9B%B8%E4%BA%A4.md)
5. [反转链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E5%8F%8D%E8%BD%AC%E9%93%BE%E8%A1%A8.md)
6. [迭代反转链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E8%BF%AD%E4%BB%A3%E5%8F%8D%E8%BD%AC%E9%93%BE%E8%A1%A8.md)
7. [回文链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E5%9B%9E%E6%96%87%E9%93%BE%E8%A1%A8.md)
8. [奇偶链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E5%A5%87%E5%81%B6%E9%93%BE%E8%A1%A8.md)
9. [链表题目](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8/%E9%93%BE%E8%A1%A8.md)



#### 字符串

1. [字符串算法模板](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2058%20-%20I.%20%E7%BF%BB%E8%BD%AC%E5%8D%95%E8%AF%8D%E9%A1%BA%E5%BA%8F.md)
2. [131. 分割回文串](https://github.com/justdoitMr/Algorithm/blob/main/Note/String/131.%20%E5%88%86%E5%89%B2%E5%9B%9E%E6%96%87%E4%B8%B2.md)



3. [验证回文串](https://github.com/justdoitMr/Algorithm/blob/main/Note/String/%E9%AA%8C%E8%AF%81%E5%9B%9E%E6%96%87%E4%B8%B2.md)

4. [有效的字母异位词](https://github.com/justdoitMr/Algorithm/blob/main/Note/String/%E6%9C%89%E6%95%88%E7%9A%84%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D.md)
5. [字符串中的第一个唯一字符](https://github.com/justdoitMr/Algorithm/blob/main/Note/String/%E5%AD%97%E7%AC%A6%E4%B8%B2%E4%B8%AD%E7%9A%84%E7%AC%AC%E4%B8%80%E4%B8%AA%E5%94%AF%E4%B8%80%E5%AD%97%E7%AC%A6.md)

---

#### 数组

1. [只出现一次的数字](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E7%BB%84/%E5%8F%AA%E5%87%BA%E7%8E%B0%E4%B8%80%E6%AC%A1%E7%9A%84%E6%95%B0%E5%AD%97.md)
2. [多数元素](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E7%BB%84/%E5%A4%9A%E6%95%B0%E5%85%83%E7%B4%A0.md)
3. [搜索二维矩阵 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E7%BB%84/%E6%90%9C%E7%B4%A2%E4%BA%8C%E7%BB%B4%E7%9F%A9%E9%98%B5%20II.md)
4. [152. 乘积最大子数组](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E7%BB%84/152.%20%E4%B9%98%E7%A7%AF%E6%9C%80%E5%A4%A7%E5%AD%90%E6%95%B0%E7%BB%84.md)
5. [189. 轮转数组](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E7%BB%84/189.%20%E8%BD%AE%E8%BD%AC%E6%95%B0%E7%BB%84.md)
6. [存在重复元素](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E7%BB%84/%E5%AD%98%E5%9C%A8%E9%87%8D%E5%A4%8D%E5%85%83%E7%B4%A0.md)
7. [移动零](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E7%BB%84/%E7%A7%BB%E5%8A%A8%E9%9B%B6.md)
8. [两个数组的交集 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E7%BB%84/%E4%B8%A4%E4%B8%AA%E6%95%B0%E7%BB%84%E7%9A%84%E4%BA%A4%E9%9B%86%20II.md)

---


### 算法

---

#### 滑动窗口

1. [滑动窗口框架](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3/%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3.md)

---

#### 动态规划

**动态规划问题步骤**

> 1. 确定dp数组（dp table）以及下标的含义
> 2. 确定递推公式
> 3. dp数组如何初始化
> 4. 确定遍历顺序
> 5. 举例推导dp数组

动态规划一定要记住的三个条件：**重叠子问题，最优子结构，状态转移方程。**

**明确「状态」 -> 定义 dp 数组/函数的含义 -> 明确「选择」-> 明确 base case。**

1. [动态规划问题框架](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92%E6%A1%86%E6%9E%B6.md)
2. [详解动态规划](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92%E8%BF%87%E7%A8%8B%E8%AF%A6%E8%A7%A3.md)
3. [动态规划的两个问题](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92%E7%9A%84%E4%B8%A4%E4%B8%AA%E9%97%AE%E9%A2%98.md)
4. [剑指 Offer II 088. 爬楼梯的最少成本.md](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/%E5%89%91%E6%8C%87%20Offer%20II%20088.%20%E7%88%AC%E6%A5%BC%E6%A2%AF%E7%9A%84%E6%9C%80%E5%B0%91%E6%88%90%E6%9C%AC.md)
5. [动态规划空间优化，机器人路径1](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92%E9%97%AE%E9%A2%98%E4%BC%98%E5%8C%96.md)
6. [63. 不同路径 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/63.%20%E4%B8%8D%E5%90%8C%E8%B7%AF%E5%BE%84%20II.md)
7. [343. 整数拆分](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/343.%20%E6%95%B4%E6%95%B0%E6%8B%86%E5%88%86.md)
8. [96. 不同的二叉搜索树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/96.%20%E4%B8%8D%E5%90%8C%E7%9A%84%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91.md)
9. [0-1背包框架一](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/0-1%E8%83%8C%E5%8C%85%E9%97%AE%E9%A2%98.md)
10. [0-1背包问题二](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/0--1%E8%83%8C%E5%8C%85%E9%97%AE%E9%A2%98.md)
11. [416. 分割等和子集](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/416.%20%E5%88%86%E5%89%B2%E7%AD%89%E5%92%8C%E5%AD%90%E9%9B%86.md)
12. [1049. 最后一块石头的重量 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/1049.%20%E6%9C%80%E5%90%8E%E4%B8%80%E5%9D%97%E7%9F%B3%E5%A4%B4%E7%9A%84%E9%87%8D%E9%87%8F%20II.md)
13. [494. 目标和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/494.%20%E7%9B%AE%E6%A0%87%E5%92%8C.md)
14. [完全背包](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/%E5%AE%8C%E5%85%A8%E8%83%8C%E5%8C%85.md)
15. [518. 零钱兑换 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/518.%20%E9%9B%B6%E9%92%B1%E5%85%91%E6%8D%A2%20II.md)
16. [377. 组合总和 Ⅳ](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/377.%20%E7%BB%84%E5%90%88%E6%80%BB%E5%92%8C%20%E2%85%A3.md)
17. [爬楼梯]()
18. [322. 零钱兑换]()
19. [279. 完全平方数]()
20. [背包问题]()
21. [198. 打家劫舍]()
22. [213. 打家劫舍 II]()
23. [121. 买卖股票的最佳时机]()
24. [122. 买卖股票的最佳时机 II]()
25. [300. 最长递增子序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/300.%20%E6%9C%80%E9%95%BF%E9%80%92%E5%A2%9E%E5%AD%90%E5%BA%8F%E5%88%97.md)
26. [674. 最长连续递增序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/674.%20%E6%9C%80%E9%95%BF%E8%BF%9E%E7%BB%AD%E9%80%92%E5%A2%9E%E5%BA%8F%E5%88%97.md)
27. [718. 最长重复子数组](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/718.%20%E6%9C%80%E9%95%BF%E9%87%8D%E5%A4%8D%E5%AD%90%E6%95%B0%E7%BB%84.md)
28. [1143. 最长公共子序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/1143.%20%E6%9C%80%E9%95%BF%E5%85%AC%E5%85%B1%E5%AD%90%E5%BA%8F%E5%88%97.md)
29. [1035. 不相交的线](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/1035.%20%E4%B8%8D%E7%9B%B8%E4%BA%A4%E7%9A%84%E7%BA%BF.md)
30. [53. 最大子数组和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/53.%20%E6%9C%80%E5%A4%A7%E5%AD%90%E6%95%B0%E7%BB%84%E5%92%8C.md)
31. [392. 判断子序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/392.%20%E5%88%A4%E6%96%AD%E5%AD%90%E5%BA%8F%E5%88%97.md)
32. [115. 不同的子序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/115.%20%E4%B8%8D%E5%90%8C%E7%9A%84%E5%AD%90%E5%BA%8F%E5%88%97.md)
33. [583. 两个字符串的删除操作](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/583.%20%E4%B8%A4%E4%B8%AA%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%9A%84%E5%88%A0%E9%99%A4%E6%93%8D%E4%BD%9C.md)
34. [72. 编辑距离](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/72.%20%E7%BC%96%E8%BE%91%E8%B7%9D%E7%A6%BB.md)
35. [647. 回文子串](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/647.%20%E5%9B%9E%E6%96%87%E5%AD%90%E4%B8%B2.md)
36. [516. 最长回文子序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92/516.%20%E6%9C%80%E9%95%BF%E5%9B%9E%E6%96%87%E5%AD%90%E5%BA%8F%E5%88%97.md)



> 注：动态规划篇很多参考labuladong的算法，只是为了记录笔记学习，没有其他任何商业用途。

---

#### 子序列类问题

---

#### 回溯法


1. [回溯法算法框架](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E5%9B%9E%E6%BA%AF%E6%B3%95(%E4%B8%80).md)
2. [回溯法详解](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E5%9B%9E%E6%BA%AF%E6%B3%95%E8%AF%A6%E8%A7%A3.md)
3. [回溯法二](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E5%9B%9E%E6%BA%AF%E6%B3%95%EF%BC%88%E4%BA%8C%EF%BC%89.md)
4. [回溯法三](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E5%9B%9E%E6%BA%AF%E6%B3%95%EF%BC%88%E4%B8%89%EF%BC%89.md)

##### 子集和组合

1. [78.子集](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/78.%20%E5%AD%90%E9%9B%86.md)
2. [90.子集 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/90.%20%E5%AD%90%E9%9B%86%20II.md)
3. [77. 组合](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/77.%20%E7%BB%84%E5%90%88.md)
4. [39.组合总和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/39.%20%E7%BB%84%E5%90%88%E6%80%BB%E5%92%8C.md)
5. [40.组合总和 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/40.%20%E7%BB%84%E5%90%88%E6%80%BB%E5%92%8C%20II.md)
6. [216. 组合总和 III](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/216.%20%E7%BB%84%E5%90%88%E6%80%BB%E5%92%8C%20III.md)
7. [93. 复原 IP 地址](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/93.%20%E5%A4%8D%E5%8E%9F%20IP%20%E5%9C%B0%E5%9D%80.md)


##### 全排列

1. [46. 全排列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/46.%20%E5%85%A8%E6%8E%92%E5%88%97.md)
2. [47. 全排列 II](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/47.%20%E5%85%A8%E6%8E%92%E5%88%97%20II.md)
3. [剑指 Offer 38. 字符串的排列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E5%89%91%E6%8C%87%20Offer%2038.%20%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%9A%84%E6%8E%92%E5%88%97.md)
4. [22. 括号生成](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E6%8B%AC%E5%8F%B7%E7%94%9F%E6%88%90.md)
5. [17、电话号码的字母组合](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/17%E3%80%81%E7%94%B5%E8%AF%9D%E5%8F%B7%E7%A0%81%E7%9A%84%E5%AD%97%E6%AF%8D%E7%BB%84%E5%90%88.md)
6. [路径和问题](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E8%B7%AF%E5%BE%84%E5%92%8C%E9%97%AE%E9%A2%98.md)

##### 回溯搜索

1. [剑指 Offer 12. 矩阵中的路径](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2012.%20%E7%9F%A9%E9%98%B5%E4%B8%AD%E7%9A%84%E8%B7%AF%E5%BE%84.md)
2. [回溯法整理](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E5%9B%9E%E6%BA%AF%E6%95%B4%E7%90%86.md)
3. [代码整理](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95/%E5%9B%9E%E6%BA%AF%E6%B3%95%E6%95%B4%E7%90%86.md)

---

#### 贪心算法

贪心算法一般分为如下四步：

1. 将问题分解为若干个子问题
2. 找出适合的贪心策略
3. 求解每一个子问题的最优解
4. 将局部最优解堆叠成全局最优解

---

#### 二分法

---

#### 双指针

---

#### 数据结构设计
1. [LFU算法](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E8%AE%BE%E8%AE%A1/LFU.md)
2. [LRU算法](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E8%AE%BE%E8%AE%A1/LRU.md)
3. [最大频率栈](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%9C%80%E5%A4%A7%E9%A2%91%E7%8E%87%E6%A0%88.md)
4. [单调栈](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8D%95%E8%B0%83%E6%A0%88.md)
5. [单调队列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84%E8%AE%BE%E8%AE%A1/%E5%8D%95%E8%B0%83%E9%98%9F%E5%88%97.md)
6. [栈实现队列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%B8%80%E3%80%81%E7%94%A8%E6%A0%88%E5%AE%9E%E7%8E%B0%E9%98%9F%E5%88%97.md)
7. [拓扑排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%88%A4%E6%96%AD%E6%9C%89%E5%90%91%E5%9B%BE%E6%98%AF%E5%90%A6%E5%AD%98%E5%9C%A8%E7%8E%AF.md)

---

### 笔记整理

1. [数据结构](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md)

2. [算法](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E7%AE%97%E6%B3%95.md)

---



