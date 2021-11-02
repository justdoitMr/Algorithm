## 填充每个节点的下一个右侧节点指针(Medium)

**题目描述**

![1635856765448](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/02/203938-800966.png)

![1635856779636](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/02/203940-692601.png)

**思路一**

使用层次遍历解决，因为在层次遍历过程中，一次循环，每一层的元素全部都在队列当中，所以可以一次从头到尾链接所有的节点，最后一个节点的next指针设置为null即可。

**完整代码**

~~~ java
class Solution {
    public Node connect(Node root) {
       
        LinkedList<Node> queue = new LinkedList<>();
        if(root == null) return root;
        queue.offer(root);

        while(!queue.isEmpty()){
            int size = queue.size();

            Node frontNode = queue.peek();
            for(int i = 1; i < size; i++){
                frontNode.next = queue.get(i);
                frontNode = frontNode.next;
            }

            for(int i = 0; i < size; i++){
                Node curNode = queue.poll();
                if(curNode.left != null) queue.offer(curNode.left);
                if(curNode.right != null) queue.offer(curNode.right);
            }
        }
        return root;
    }
}
~~~

**思路二**

深度优先遍历，父节点的两个孩子节点我们 好处理，但是对于示例中节点5和节点6很显然他们不属于一个父节点，我们无法处理，所以在这里我们使用辅助函数，链接两个节点。

**完整代码**

~~~ java
class Solution {
    public Node connect(Node root) {
        // base 条件
        if(root == null){
            return null;
        }
        if(root.next == null){
            root.next=null;
        }
      connectTwoNode(root.left,root.right);
        return root;
        
    }
    // 链接两个节点
    void connectTwoNode(Node node1,Node node2){
        if(node1 == null || node2 == null)
            return ;
        node1.next=node2;
        connectTwoNode(node1.left,node1.right);
        connectTwoNode(node2.left,node2.right);
        connectTwoNode(node1.right,node2.left);
    }

}
~~~

