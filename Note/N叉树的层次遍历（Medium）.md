## N叉树的层次遍历（Medium）

**题目描述**

![1635854847313](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/02/200728-881252.png)

**思路**

和普通二叉树的层次遍历类似，借助于队列进行层次遍历，唯一不同的是二叉树的孩子右左右孩子，二N叉树的孩子节点个数是不确定的，所以在从队列当中拿到一个节点的时候，要遍历其孩子节点，依次入队列。

**完整代码**

~~~ java
class Solution {
    public List<List<Integer>> levelOrder(Node root) {

        // 定义结果集
        List<List<Integer>> res = new ArrayList<>();
        
        if(root == null){
            return res;
        }
        // 定义队列
        Queue<Node> queue = new LinkedList<>();
        // 根节点入队列
        queue.offer(root);
        while(!queue.isEmpty()){
            ArrayList<Integer> temp=new ArrayList<>();
            int sz=queue.size();
            for(int i=0;i< sz;i++){
                Node node=queue.poll();
                temp.add(node.val);
                for(Node n:node.children){
                    if(n != null){
                        queue.offer(n);
                    }
                }
            }
            res.add(temp);
        }
        return res;
    }
}
~~~



