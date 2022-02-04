## 二叉树的层平均值(Easy)

### [637. 二叉树的层平均值](https://leetcode-cn.com/problems/average-of-levels-in-binary-tree/)

**题目描述**

![1635854316240](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/10/081852-963164.png)

**思路**

本题更多是考察数据类型，所以定义和变量的时候定义为double类型即可。

**完整代码**

~~~ java
class Solution {
    public List<Double> averageOfLevels(TreeNode root) {

        // 声明结果数组
        List<Double> res = new ArrayList<>();
        if(root == null){
            return null;
        }
        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(root);
        while(!queue.isEmpty()){
            int num=0;
            Double sum = 0.0;
            int sz=queue.size();
            for(int i=0;i< sz;i++){
                TreeNode node = queue.poll();
                sum += node.val;
                num++;
                if(node.left != null){
                    queue.offer(node.left);
                }
                if(node.right != null){
                    queue.offer(node.right);
                }
            }
            res.add(sum/num);
        }
        return res;

    }
}
~~~

