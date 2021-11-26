## 剑指 Offer 36. 二叉搜索树与双向链表

### [剑指 Offer 36. 二叉搜索树与双向链表](https://leetcode-cn.com/problems/er-cha-sou-suo-shu-yu-shuang-xiang-lian-biao-lcof/)

### 递归法

![1637923395381](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/26/184316-22043.png)

二叉搜索树的中序遍历就是有序的，因此这道题就是在中序递归遍历的基础上改了一点。

**具体过程**

1. 我们定义两个指针`pre`和`head`，`pre`指针用于保存中序遍历的前一个节点，`head`指针用于记录排序链表的头节点。
2. 中序遍历二叉树，因为是中序遍历，所以遍历顺序就是双线链表的建立顺序。我们只需要在中序遍历的过程中，修改每个节点的左右指针，将零散的节点连接成双向循环链表。

![1637923458328](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/26/184419-450945.png)

3. 首先遍历二叉树的左子树，然后是当前根节点root。

- 当前驱节点pre不为空时，将前驱节点pre的右指针指向当前根节点root，即pre->right = root。

![1637923507625](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/26/184508-696574.png)

- 当前驱节点`pre`为空时： 代表正在访问链表头节点，记为 `head = root `，保存头节点。

4. 每一个root节点访问时它的左子树肯定被访问过了，因此放心修改它的left指针，将root的left指针指向它的前驱节点，即 root->left = pre， 这样两个节点之间的双向指针就修改好了。

![1637923554938](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/26/184555-429690.png)

5. 然后前驱节点`pre`右移到当前`root`节点，接下来递归到右子树重复上述操作。

![1637923584338](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/26/184624-480913.png)

6. 完成以上各步，只是将二叉树变成了双向排序链表，我们还需要将链表的首尾连接到一起，将其变成双向循环排序链表。

执行以下操作：

~~~ java
head->left = pre;
pre->right = head
~~~

时间复杂度是o(n)

**完整代码**

~~~ java
class Solution {
    Node pre = null;
    Node head = null;
    public Node treeToDoublyList(Node root) {
        if(root == null){
            return root;
        }
        treeToDoublyList_A(root);
        head.left =pre;
        pre.right=head;
        return head;
        
    }

    public void treeToDoublyList_A(Node root) {

        if(root == null){
            return ;
        }
        treeToDoublyList_A(root.left);
        if(pre != null){
            pre.right = root;
        }else{
            head = root;
        }
        // 记录前一个节点
        root.left=pre;
        pre = root;
        treeToDoublyList_A(root.right);
    }
}
~~~

