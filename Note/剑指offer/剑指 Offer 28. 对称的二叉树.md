## 剑指 Offer 28. 对称的二叉树

### [剑指 Offer 28. 对称的二叉树](https://leetcode-cn.com/problems/dui-cheng-de-er-cha-shu-lcof/)

### 对称遍历法

既然是一颗对称的二叉树，那么前序遍历中左右，对称遍历中右左，遍历得到的结果应该是一样的，所以基于这个原理，可以对二叉树进行前序遍历和对称遍历，然后查看结果元素是不是相对应一样。

但是有一点情况，如果二叉树所有节点的值都是一样的，遍历出来的两个序列肯定一样，所以这时候我们就需要考虑空节点的值了，我们也需要把空节点使用一个标记记录，然后在比较。

**完整代码**

~~~ java
class Solution {
    ArrayList<Integer> res1=new ArrayList();
    ArrayList<Integer> res2 = new ArrayList();
    public boolean isSymmetric(TreeNode root) {

        isSymmetric_A(root);
        isSymmetric_B(root);
        
        if(res1.size()!= res2.size()){
            return false;
        }
        for(int i=0;i<res1.size();i++){
            if(res1.get(i) != res2.get(i)){
                return false;
            }
        }

        return true;


    }

//  定义前序遍历二叉树
    public void isSymmetric_A(TreeNode root) {

        if(root == null){
            res1.add(-1);
            return ;
        }
        res1.add(root.val);
        isSymmetric_A(root.left);
        isSymmetric_A(root.right);
    }

    // 定义对称遍历二叉树
    public void isSymmetric_B(TreeNode root){
        
        if(root == null){
            res2.add(-1);
            return ;
        }
        res2.add(root.val);
        isSymmetric_B(root.right);
        isSymmetric_B(root.left);
    }
}
~~~

另外也有递归法，迭代法都可以实现。

通过本题目，需要记住不光只有二叉树的前中后遍历，有时候我们也可以对这三种遍历方式进行变形。