## 剑指 Offer 26. 树的子结构

### [剑指 Offer 26. 树的子结构](https://leetcode-cn.com/problems/shu-de-zi-jie-gou-lcof/)

### 递归法

如何判断`root2`是否是`root1`的子树，我们可以拆分为两步：

1. 首先判断在root1中是否存在以root2为根的节点，这一步可以归结为在root1中的查找，查找以root2为根的节点值是否在root1树中，这一步采用前序，中序，后续遍历都可以。
2. 第二步就是判断树的结构以及节点的值是否是一样的，在第一步的基础上，如果在root1中找到存在的节点，那么这一步就开始判断树的结构以及节点的值是否相同。每次遍历到两棵树的某一个节点，我们有一下判断：

1. **如果两个节点都是空节点，那么说明结构是一样的，可以返回true**

~~~ java
 if(A == null && B == null){
            return true;
        }
~~~

2. **如果root1 == null && root2 != null，那么这种情况我们返回false,因为我们判断的是root2是否是root1的子树，所以如果root1为空，root2不是空，那么root2为根节点的树不可能是root1的子树**

~~~ java
if(A == null && B!= null){
    return false;
}
~~~

3. **如果root1 != null && root2 == null，那么这种情况我们返回true，因为root2可能是root1的子树**

~~~ java
if( A != null && B == null){
  return true;
}
~~~

4. **最后一种情况就是两个节点都不是空节点，那么我们就判断此时两个节点值是否是一样的，如果不一样就返回false**

~~~ java
if(A.val != B.val){
   return false;
}
~~~

5. **对于递归体部分，我们依次递归两棵树的左孩子和右孩子即可**

~~~ java
// 判断左右子树是否一样
         boolleft=isSubStructure_A(A.left,B.left);
         boolright=isSubStructure_A(A.right,B.right);
~~~

**完整代码**

~~~ java
class Solution {

   boolean res=false;
    public boolean isSubStructure(TreeNode A, TreeNode B) {


        hasRoot(A,B);
        return res;
    }

    // 首先判断在树A中是否存在树B的根节点
    public void hasRoot(TreeNode A,TreeNode B){

        // 递归出口
        if(A == null || B==null){
            return ;
        }
        if(A.val == B.val){
            // 判断子树是否相等
            res=isSubStructure_A(A,B);
        }
        // 递归搜索左子树
        hasRoot(A.left,B);
        hasRoot(A.right,B);

        return ;
    }
    boolean boolleft=false;
    boolean boolright=false;
    public boolean isSubStructure_A(TreeNode A, TreeNode B) {
        
      if(A == null && B == null){
            return true;
        }else if( A != null && B == null){
            return true;
        }else if(A == null && B!= null){
            return false;
        }else if(A.val != B.val){
           return false;
        }
         // 判断左右子树是否一样
         boolleft=isSubStructure_A(A.left,B.left);
         boolright=isSubStructure_A(A.right,B.right);
        
        return boolleft&&boolright;
    }

}
~~~

### 拓展

从这个题目中，我们可以提出如何判断两棵树的结构是否一样的代码片段：

~~~ java
/**
     * 判断以A,B为根的两棵树的结构是否是一样的
     * @param A
     * @param B
     * @return
     */
    public boolean isSubStructure(TreeNode A, TreeNode B) {
        
        // 如果两个节点都是空，那么结构肯定一样，返回true
        if(A == null && B == null){
            return true;
            // 两个节点有一个节点为空，那么就说明结构式不一样的
        }else if( A != null && B == null){
            return false;
            // 同样，如果有一个节点为空，说明结构式不一样的
        }else if(A == null && B!= null){
            return false;
            // 隐含条件是两个节点都不是空的情况，我们在这里就做一个判断，节点值是否一样
            // 具体的可以根据题目条件进行设定
        }else if(A.val != B.val){
           return false;
        }
         // 判断左右子树的结构是否是一样的
         boolleft=isSubStructure_A(A.left,B.left);
         boolright=isSubStructure_A(A.right,B.right);
        
        return boolleft&&boolright;
    }
~~~

