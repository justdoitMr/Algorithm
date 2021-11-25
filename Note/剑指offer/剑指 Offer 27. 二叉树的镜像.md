## 剑指 Offer 27. 二叉树的镜像

### [剑指 Offer 27. 二叉树的镜像](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)

### 递归法

递归三步法：

**递归函数参数和返回值**

考虑递归函数参数和返回值，我们需要返回二叉树镜像的根节点，所以返回类型是TreeNode类型，而参数就是需要镜像的二叉树。

**递归函数出口**

当我们遍历到一个空节点的时候，该如何操作？ 很明显，我们返回空值，什么也不做即可。

**递归函数体**

当我们遇到一个节点，按照题目的意思，交换左右孩子指针的指向即可，所以很容易写出完整代码。

**完整代码**

~~~ java 
class Solution {
    public TreeNode mirrorTree(TreeNode root) {


        return mirrorTree_A(root);
    }


     public TreeNode mirrorTree_A(TreeNode root) {

         if(root == null){
             return null;
         }
        TreeNode temp=root.left;
        root.left = root.right;
        root.right = temp;
        //分别递归交换左右
        mirrorTree_A(root.left);
        mirrorTree_A(root.right);

        return root;
    }
}
~~~

