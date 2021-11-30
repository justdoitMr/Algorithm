## 剑指 Offer 55 - II. 平衡二叉树

### [剑指 Offer 55 - II. 平衡二叉树](https://leetcode-cn.com/problems/ping-heng-er-cha-shu-lcof/)

### 递归法

~~~ java
	class Solution {
   public boolean isBalanced(TreeNode root) {
        if (root == null) {
            return true;
        }

        // 先判断左右两个子树是否平衡，不平衡的话返回false
        int l = treeDeepth(root.left);
        int r = treeDeepth(root.right);
        if (Math.abs(l - r) > 1) {
            return false;
        }

        // 然后在继续判断他的左右子树是否平衡（前序遍历）
        return isBalanced(root.left) && isBalanced(root.right);
    }

    public int treeDeepth(TreeNode root) {
        if (root == null) {
            return 0;
        }

        int l = treeDeepth(root.left);
        int r = treeDeepth(root.right);

        return 1 + Math.max(l, r);
    }
}
~~~

递归算法的时间复杂度：

- isBalanced()算法时间复杂度是logn，因为要判断每一层是否平衡。
- 递归体的算法时间复杂度是o(n)，因为针对每一个节点，都需要访问以下节点的高度，右n个节点。

所以总的时间复杂度是o(nlogn)