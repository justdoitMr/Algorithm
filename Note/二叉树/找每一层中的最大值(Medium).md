
## 找每一层中的最大值(Medium)

**题目描述**

[剑指 Offer II 044. 二叉树每层的最大值](https://leetcode-cn.com/problems/hPov7L/)

![1635855374687](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/02/201615-834857.png)

**思路**

还是层次遍历，遍历每一层时候，相互比较找到最大值。

**完整代码**

~~~ java
class Solution {
    public List<Integer> largestValues(TreeNode root) {
        // 声明结果数组
        List<Integer> res = new ArrayList<>();
        if (root == null) {
            return res;
        }
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        while (!queue.isEmpty()) {
            int max=Integer.MIN_VALUE;
            int sz = queue.size();
            for (int i = 0; i < sz; i++) {
                TreeNode node = queue.poll();
              if(node.val > max){
                  max= node.val;
              }
                if (node.left != null) {
                    queue.offer(node.left);
                }
                if (node.right != null) {
                    queue.offer(node.right);
                }
            }
            res.add(max);
        }
        return res;
    }
}
~~~

**思路二**

也可以考虑使用深度优先遍历，深度遍历树，保存每一层的数值，然后找出每一层的最大值即可。