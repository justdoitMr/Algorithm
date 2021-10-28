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

### 算法

---

在这一部分，我将会更新一些常用的算法技巧，掌握一些算法技巧不是偷懒，而是为了更好的刷题，更高效的去解答每一道题目，可以帮助我们迅速的去定位一些问题的解法，常用的一些技巧，比如：双指针，二分查找，滑动窗口，递归等等，并且还会借鉴网上的一些模板，形成自己的一套接替思路，希望可以帮到大家。

> 注：本人在学习算法阶段，笔记是参考博主`labuladong`,还是非常感谢这位大神的方法和技巧，让我受益匪浅，下面的笔记是参考这位博主的，加了一些自己的观点和代码补充。

---

#### BFS

1. [BFS算法技巧(一)](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS.md)
2. [BFS算法技巧(二)](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS%EF%BC%88%E4%BA%8C%EF%BC%89.md)
3. [BFS和DFS](https://github.com/justdoitMr/Algorithm/blob/main/Note/DFS%E5%92%8CBFS.md)

#### 二叉树

##### 二叉树

1. [二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91(%E4%B8%80).md)
2. [二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91%EF%BC%88%E4%BA%8C%EF%BC%89.md)
3. [二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91%EF%BC%88%E4%B8%89%EF%BC%89.md)
4. [二叉树序列化](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91%E5%BA%8F%E5%88%97%E5%8C%96.md)
5. [二叉树最近公共祖先](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91%E6%9C%80%E8%BF%91%E5%85%AC%E5%85%B1%E7%A5%96%E5%85%88.md)
6. [最大键值和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%9C%80%E5%A4%A7%E9%94%AE%E5%80%BC%E5%92%8C.md)
7. [计算二叉树的高度](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E8%AE%A1%E7%AE%97%E4%BA%8C%E5%8F%89%E6%A0%91%E9%AB%98%E5%BA%A6.md)
8. [二叉树非递归遍历](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E9%9D%9E%E9%80%92%E5%BD%92%E6%96%B9%E5%BC%8F%E9%81%8D%E5%8E%86.md)
9. [反转二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8F%8D%E8%BD%AC%E4%BA%8C%E5%8F%89%E6%A0%91.md)

##### 二叉搜索树

1. [二叉搜索树(一)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%B8%80%EF%BC%89.md)
2. [二叉搜树(二)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%BA%8C%EF%BC%89.md)
3. [二叉搜索树(三)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%B8%89%EF%BC%89.md)

#### 链表

1. [这些链表使用技巧，一定要掌握！](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8.md)

#### 滑动窗口

1. [高效使用滑动窗口](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%BB%91%E5%8A%A8%E7%AA%97%E5%8F%A3.md)

#### 动态规划

1. [动态规划问题框架](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92%E6%A1%86%E6%9E%B6.md)
2. [动态规划两个问题](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92%E7%9A%84%E4%B8%A4%E4%B8%AA%E9%97%AE%E9%A2%98.md)
3. [动态规划举例](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8A%A8%E6%80%81%E8%A7%84%E5%88%92%E8%BF%87%E7%A8%8B%E8%AF%A6%E8%A7%A3.md)
4. [爬楼梯](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E7%88%AC%E6%A5%BC%E6%A2%AF.md)
5. [最大子序列和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%9C%80%E5%A4%A7%E5%AD%90%E5%BA%8F%E5%88%97%E5%92%8C.md)
6. [最长公共子序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%9C%80%E9%95%BF%E5%85%AC%E5%85%B1%E5%AD%90%E5%BA%8F%E5%88%97.md)
7. [最长连续递增子序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%9C%80%E9%95%BF%E8%BF%9E%E7%BB%AD%E9%80%92%E5%A2%9E%E5%BA%8F%E5%88%97.md)
8. [最长回文子串](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%9C%80%E9%95%BF%E5%9B%9E%E6%96%87%E5%AD%90%E4%B8%B2.md)
9. [最长回文子序列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%9C%80%E9%95%BF%E5%9B%9E%E6%96%87%E5%AD%90%E5%BA%8F%E5%88%97.md)

#### 回溯法

1. [彻底理解回溯法算法思想](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95.md)
2. [回溯法(一)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95%E8%AF%A6%E8%A7%A3.md)
3. [回溯法(二)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95%EF%BC%88%E4%BA%8C%EF%BC%89.md)
4. [回溯法(三)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%9B%9E%E6%BA%AF%E6%B3%95%EF%BC%88%E4%B8%89%EF%BC%89.md)
5. [括号生成](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%8B%AC%E5%8F%B7%E7%94%9F%E6%88%90.md)

#### 贪心算法

1. [贪心算法思想](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E8%B4%AA%E5%BF%83%E7%AE%97%E6%B3%95.md)

#### 二分法

1. [二分法详解](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%88%86%E6%9F%A5%E6%89%BE.md)

### 字符串专题

1. [1456、定长子串中元音字母最大个数](https://github.com/justdoitMr/Algorithm/blob/main/Note/String/1456-Medium.md)

### 链表专题

[技巧](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%93%BE%E8%A1%A8.md)

[迭代法反转链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E8%BF%AD%E4%BB%A3%E5%8F%8D%E8%BD%AC%E9%93%BE%E8%A1%A8.md)

[递归法反转链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E9%80%92%E5%BD%92%E5%8F%8D%E8%BD%AC%E6%95%B4%E4%B8%AA%E9%93%BE%E8%A1%A8.md)

### 树专题



### 数组专题



### 笔记整理

1. [数据结构](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md)

2. [算法](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E7%AE%97%E6%B3%95.md)