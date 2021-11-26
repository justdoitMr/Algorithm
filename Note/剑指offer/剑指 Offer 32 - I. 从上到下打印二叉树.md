## 剑指 Offer 32 - I. 从上到下打印二叉树

### [剑指 Offer 32 - I. 从上到下打印二叉树](https://leetcode-cn.com/problems/cong-shang-dao-xia-da-yin-er-cha-shu-lcof/)

### BFS遍历

**完整代码**

~~~ java
	class Solution {
    public int[] levelOrder(TreeNode root) {

        return levelOrder_A(root);

    }

    public int[] levelOrder_A(TreeNode root) {

        int res []={};
        if(root == null){
            return res;
        }
        ArrayList<Integer> list = new ArrayList();
        Queue<TreeNode> queue =new LinkedList();
        queue.add(root);
        while(!queue.isEmpty()){
            int sz= queue.size();
            for(int i=0;i<sz;i++){
                TreeNode node = queue.poll();
                list.add(node.val);
                if(node.left!= null){
                    queue.offer(node.left);
                }
                if(node.right != null){
                    queue.offer(node.right);
                }
            }
        }
        res =new int[list.size()];

        for(int i=0;i<list.size();i++){
            res[i]=list.get(i);
        }
        return res;

    }
}
~~~

