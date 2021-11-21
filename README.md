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
### 剑指Offer

#### 数据结构

1. [剑指 Offer 03. 数组中重复的数字](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2003.%20%E6%95%B0%E7%BB%84%E4%B8%AD%E9%87%8D%E5%A4%8D%E7%9A%84%E6%95%B0%E5%AD%97.md)
2. [剑指 Offer 04. 二维数组中的查找](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2004.%20%E4%BA%8C%E7%BB%B4%E6%95%B0%E7%BB%84%E4%B8%AD%E7%9A%84%E6%9F%A5%E6%89%BE%5D.md)
3. [剑指 Offer 05. 替换空格](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2005.%20%E6%9B%BF%E6%8D%A2%E7%A9%BA%E6%A0%BC.md)
4. [剑指 Offer 06. 从尾到头打印链表](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2006.%20%E4%BB%8E%E5%B0%BE%E5%88%B0%E5%A4%B4%E6%89%93%E5%8D%B0%E9%93%BE%E8%A1%A8.md)
5. [剑指 Offer 07. 重建二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2007.%20%E9%87%8D%E5%BB%BA%E4%BA%8C%E5%8F%89%E6%A0%91.md)
6. [剑指 Offer 09. 用两个栈实现队列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2009.%20%E7%94%A8%E4%B8%A4%E4%B8%AA%E6%A0%88%E5%AE%9E%E7%8E%B0%E9%98%9F%E5%88%97.md)

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


13. [高质量代码](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E9%AB%98%E8%B4%A8%E9%87%8F%E4%BB%A3%E7%A0%81.md)
14. [剑指 Offer 16. 数值的整数次方](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2016.%20%E6%95%B0%E5%80%BC%E7%9A%84%E6%95%B4%E6%95%B0%E6%AC%A1%E6%96%B9.md)
15. [剑指 Offer 17. 打印从1到最大的n位数]()
16. [剑指 Offer 18. 删除链表的节点](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%89%91%E6%8C%87offer/%E5%89%91%E6%8C%87%20Offer%2018.%20%E5%88%A0%E9%99%A4%E9%93%BE%E8%A1%A8%E7%9A%84%E8%8A%82%E7%82%B9.md)


---

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
8. [二叉树左叶子之和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/404%E3%80%81%E5%B7%A6%E5%8F%B6%E5%AD%90%E4%B9%8B%E5%92%8C.md)
9. [找树左下角的值](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/513%E3%80%81%E6%89%BE%E6%A0%91%E5%B7%A6%E4%B8%8B%E8%A7%92%E7%9A%84%E5%80%BC.md)
10. [路径总和](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/112%E3%80%81%E8%B7%AF%E5%BE%84%E6%80%BB%E5%92%8C1.md)
11. [合并二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/617%E3%80%81%E5%90%88%E5%B9%B6%E4%BA%8C%E5%8F%89%E6%A0%91.md)
12. [二叉搜索树中的搜索](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/700%E3%80%81%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E4%B8%AD%E7%9A%84%E6%90%9C%E7%B4%A2.md)
13. [二叉树的序列化](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E5%BA%8F%E5%88%97%E5%8C%96.md)
14. [二叉搜索树(一)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%B8%80%EF%BC%89.md)
15. [二叉搜索树(二)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%BA%8C%EF%BC%89.md)
16. [二叉搜索树(三)](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%EF%BC%88%E4%B8%89%EF%BC%89.md)


##### 基础算法


##### BFS

1. [BFS(一)](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/BFS(%E4%B8%80).md)
2. [BFS(二)](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/BFS%EF%BC%88%E4%BA%8C%EF%BC%89.md)
3. [BFS和DFS](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/DFS%E5%92%8CBFS.md)
4. [判断有向图中是否有环](https://github.com/justdoitMr/Algorithm/blob/main/Note/BFS/%E5%88%A4%E6%96%AD%E6%9C%89%E5%90%91%E5%9B%BE%E6%98%AF%E5%90%A6%E5%AD%98%E5%9C%A8%E7%8E%AF.md)
5. [二叉树的右视图](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E5%8F%B3%E8%A7%86%E5%9B%BE.md)
6. [填充每个节点的下一个右侧节点指针](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%A1%AB%E5%85%85%E6%AF%8F%E4%B8%AA%E8%8A%82%E7%82%B9%E7%9A%84%E4%B8%8B%E4%B8%80%E4%B8%AA%E5%8F%B3%E4%BE%A7%E8%8A%82%E7%82%B9%E6%8C%87%E9%92%88(Medium).md)
7. [找每一层中的最大值](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E6%89%BE%E6%AF%8F%E4%B8%80%E5%B1%82%E4%B8%AD%E7%9A%84%E6%9C%80%E5%A4%A7%E5%80%BC(Medium).md)
8. [N叉树的层次遍历](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/N%E5%8F%89%E6%A0%91%E7%9A%84%E5%B1%82%E6%AC%A1%E9%81%8D%E5%8E%86%EF%BC%88Medium%EF%BC%89.md)

##### DFS

1. [对称二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%AF%B9%E7%A7%B0%E4%BA%8C%E5%8F%89%E6%A0%91(Easy).md)
2. [求二叉树的深度](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E6%B7%B1%E5%BA%A6(Easy).md)
3. [**二叉树中所有路径**](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E6%89%80%E6%9C%89%E8%B7%AF%E5%BE%84.md)
4. [**二叉树的最近公共祖先**](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E4%BA%8C%E5%8F%89%E6%A0%91%E6%9C%80%E8%BF%91%E5%85%AC%E5%85%B1%E7%A5%96%E5%85%88.md)
5. [反转二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%8F%8D%E8%BD%AC%E4%BA%8C%E5%8F%89%E6%A0%91.md8)
6. [完全二叉树节点个数](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%AE%8C%E5%85%A8%E4%BA%8C%E5%8F%89%E6%A0%91%E7%9A%84%E8%8A%82%E7%82%B9%E4%B8%AA%E6%95%B0.md)
7. [判断是否是平衡二叉树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E5%88%A4%E6%96%AD%E6%98%AF%E5%90%A6%E6%98%AF%E5%B9%B3%E8%A1%A1%E4%BA%8C%E5%8F%89%E6%A0%91.md)
8. [**最大键值和**](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/%E6%9C%80%E5%A4%A7%E9%94%AE%E5%80%BC%E5%92%8C.md)
9. [530、二叉搜索树的最小绝对差.md](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/530%E3%80%81%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E7%9A%84%E6%9C%80%E5%B0%8F%E7%BB%9D%E5%AF%B9%E5%B7%AE.md)
10. [701、二叉搜索树中的插入](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/701%E3%80%81%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E4%B8%AD%E7%9A%84%E6%8F%92%E5%85%A5.md)
11. [450、二叉搜索树中的删除](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/450%E3%80%81%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91%E4%B8%AD%E7%9A%84%E5%88%A0%E9%99%A4.md)
12. [108.将有序数组转换为二叉搜索树](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%BA%8C%E5%8F%89%E6%A0%91/108%E3%80%81%E5%B0%86%E6%9C%89%E5%BA%8F%E6%95%B0%E7%BB%84%E8%BD%AC%E6%8D%A2%E4%B8%BA%E4%BA%8C%E5%8F%89%E6%90%9C%E7%B4%A2%E6%A0%91.md)




---

#### 链表

#### 字符串

---

#### 数组

---


### 算法

---

#### 滑动窗口

---

#### 动态规划

---

#### 子序列类问题

---

#### 回溯法

---

#### 贪心算法

---

#### 二分法

---

#### 双指针

---

#### 数据结构设计
1. [LFU算法](https://github.com/justdoitMr/Algorithm/blob/main/Note/LFU.md)
2. [LRU算法](https://github.com/justdoitMr/Algorithm/blob/main/Note/LRU.md)
3. [最大频率栈](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%9C%80%E5%A4%A7%E9%A2%91%E7%8E%87%E6%A0%88.md)
4. [单调栈](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8D%95%E8%B0%83%E6%A0%88.md)
5. [单调队列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%8D%95%E8%B0%83%E9%98%9F%E5%88%97.md)
6. [栈实现队列](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E4%B8%80%E3%80%81%E7%94%A8%E6%A0%88%E5%AE%9E%E7%8E%B0%E9%98%9F%E5%88%97.md)
7. [拓扑排序](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E5%88%A4%E6%96%AD%E6%9C%89%E5%90%91%E5%9B%BE%E6%98%AF%E5%90%A6%E5%AD%98%E5%9C%A8%E7%8E%AF.md)

---

### 笔记整理

1. [数据结构](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E6%95%B0%E6%8D%AE%E7%BB%93%E6%9E%84.md)

2. [算法](https://github.com/justdoitMr/Algorithm/blob/main/Note/%E7%AE%97%E6%B3%95.md)

---



