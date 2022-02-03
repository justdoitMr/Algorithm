## 剑指offer面试题8：二叉树的下一个节点

### 思路

1. 如果该节点有右子树，那么中序遍历的下一个值为右子树的最左节点 
2. 如果该节点的右子树为空，但是是父节点的左子节点，则父节点是其下一个节点；
3. 如果该节点的右子树为空，但是不是父节点的左子节点，那么就找到父节点的父节点，直到当前节点处于父节点的左子树，否则他就是尾节点。

**完整代码**

~~~java
public class Solution{
    TreeLinkNode GetNext(TreeLinkNode node){
        if(node == null){
            return null;
        }
        if(node.right !=  null){
            node = node.right;
            while(node.left != null){
                node = node.left;
            }
            return node;
        }
        while(node.next != null){
            if(node.next.left == node){
                return node.next;
            }
            node = node.next;
        }
        return null;
    }
}
~~~

