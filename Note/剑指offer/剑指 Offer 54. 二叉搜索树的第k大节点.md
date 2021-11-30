## 剑指 Offer 54. 二叉搜索树的第k大节点

### [剑指 Offer 54. 二叉搜索树的第k大节点](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-de-di-kda-jie-dian-lcof/)

### 右中左遍历法

~~~ java
class Solution {
     int count = 0;
    int val=0;
    public int kthLargest(TreeNode root, int k) {

       kthLargest_A(root,k);
       return val;
    }   

//  使用右中左遍历法
   
    public void kthLargest_A(TreeNode root, int k) {

        if(root == null){
            return ;
        }
        
        kthLargest_A(root.right,k);
        count++;
        if(count == k){
            val = root.val;
            return;
        }
        kthLargest_A(root.left,k);

    }
}
~~~

### 中序非递归实现

~~~ java
public int kthLargest_B(TreeNode root, int k) {

        if(root == null){
            return 0;
        }

        Stack<TreeNode> stack = new Stack<>();
        TreeNode p =root;
        while(!stack.isEmpty()|| p!= null){
            if(p!=null){
                stack.push(p);
                p=p.right;
            }else{
                p=stack.pop();
                k--;
                // 中序访问元素
                if(k == 0){
                    return p.val;
                }
                p=p.left;

            }
        }
        return 0;

    }
~~~

