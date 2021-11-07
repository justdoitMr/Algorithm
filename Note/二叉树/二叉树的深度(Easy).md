## 二叉树的深度(Easy)

### 二叉树的最大深度

**题目描述**

求一颗二叉树的最大深度。

**思路一**

使用递归的方法，很容易写出代码。

**完整代码**

~~~ java
class Solution {
    public int maxDepth(TreeNode root) {
         if(root == null){
             return 0;
         }
         int left=maxDepth(root.left)+1;
         int right=maxDepth(root.right)+1;

         return Math.max(left, right);
    }
}

~~~

**思路二**

使用层次遍历，层次遍历的结果集中元素的个数就是树的高度。

**完整代码**

~~~ java
class Solution {
    public int maxDepth(TreeNode root) {
        return getHeightByBfs(root);
    }

    // 也可以使用层次遍历
    int getHeightByBfs(TreeNode root){
         // 声明结果集
         List<List<Integer>> res=new ArrayList<>();
 
         // 声明一个队列
         Queue<TreeNode> queue = new LinkedList<>();
 
         // 先层次遍历，结果存储到栈中，然后在返回结果即可
         if(root == null){
             return 0;
         }
         // 树根节点入队列
         queue.offer(root);
         while(!queue.isEmpty()){
             // 计算每一层元素个数
             ArrayList<Integer> temp = new ArrayList<>();
             int sz=queue.size();
             for(int i=0;i<sz;i++){
                 // 抛出队列当中的元素
                 TreeNode node=queue.poll();
                 temp.add(node.val);
 
                 if(node.left != null){
                     queue.offer(node.left);
                 }
                 if(node.right != null){
                     queue.offer(node.right);
                 }
             }
             res.add(temp);
         }
        
         return res.size();
    }
}

~~~

### 二叉树的最小深度

**题目描述**

![1635860706777](C:\Users\MrR\AppData\Roaming\Typora\typora-user-images\1635860706777.png)

给定一颗二叉树，求其最小深度。

**思路一**

使用层次遍历的方法，当第一次遇到一个灭有左右孩子节点的父节点，就是二叉树的最小深度。

**完整代码**

~~~ java
class Solution {
    public int minDepth(TreeNode root) {
        if(root == null)
        {
            return 0;
        }    
//    使用广度优先遍历
    Queue<TreeNode> q=new LinkedList<>();
    q.add(root);
    int hight=0;
    while(!q.isEmpty()){
        // 获取某一层元素的个数
        int sz=q.size();
        hight++;

        for(int i=0;i<sz;i++){
            TreeNode node= q.poll();
            if(node.left == null && node.right == null){
                return hight;
            }
            if(node.left != null){
                q.add(node.left);
            }
            if(node.right != null){
                q.add(node.right);
            }

        }
    }
    return 0;

    }
}
~~~

**思路二**

深度优先遍历

**完整代码**

~~~ java
class Solution {
    public int minDepth(TreeNode root) {
        if(root == null)
        {
            return 0;
        }    
    		return getDepth(root);
    }
    // 深度优先遍历

    int getDepth(TreeNode root){
        if(root == null){
            return 0;
        }
        int leftDepth=getDepth(root.left);
        int rightDepth=getDepth(root.right);

        if(root.left != null && root.right == null){
            return leftDepth +1;
        }
        if(root.left == null && root.right != null){
            return rightDepth+1;
        }
        return Math.min(leftDepth, rightDepth)+1;
    }
}
~~~

