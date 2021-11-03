## 对称二叉树(Easy)

**题目描述**

![1635903220882](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/03/093342-134715.png)

**递归法**

> 递归三个步骤：
>
> 1. 确定递归函数的参数和返回值
> 2. 确定递归出口
> 3. 确定递归逻辑

**确定递归函数的参数和返回值**

因为我们要比较的是根节点的两个子树是否是相互翻转的，进而判断这个树是不是对称树，所以要比较的是两个树，参数自然也是左子树节点和右子树节点。

返回值自然是bool类型。

代码如下：

```java
bool compare(TreeNode left, TreeNode right)
```

**确定终止条件**

要比较两个节点数值相不相同，首先要把两个节点为空的情况弄清楚！否则后面比较数值的时候就会操作空指针了。

节点为空的情况有：（**注意我们比较的其实不是左孩子和右孩子，所以如下我称之为左节点右节点**）

- 左节点为空，右节点不为空，不对称，return false
- 左不为空，右为空，不对称 return false
- 左右都为空，对称，返回true

此时已经排除掉了节点为空的情况，那么剩下的就是左右节点不为空：

- 左右都不为空，比较节点数值，不相同就return false

此时左右节点不为空，且数值也不相同的情况我们也处理了。

代码如下：

```java
if (left == NULL && right != NULL) return false;
else if (left != NULL && right == NULL) return false;
else if (left == NULL && right == NULL) return true;
else if (left->val != right->val) return false; // 注意这里我没有使用else
```

注意上面最后一种情况，我没有使用else，而是elseif， 因为我们把以上情况都排除之后，剩下的就是 左右节点都不为空，且数值相同的情况。

**确定单层递归的逻辑**

此时才进入单层递归的逻辑，单层递归的逻辑就是处理 左右节点都不为空，且数值相同的情况。

- 比较二叉树外侧是否对称：传入的是左节点的左孩子，右节点的右孩子。
- 比较内测是否对称，传入左节点的右孩子，右节点的左孩子。
- 如果左右都对称就返回true ，有一侧不对称就返回false 。

代码如下：

```cpp
bool outside = compare(left->left, right->right);   // 左子树：左、 右子树：右
bool inside = compare(left->right, right->left);    // 左子树：右、 右子树：左
bool isSame = outside && inside;                    // 左子树：中、 右子树：中（逻辑处理）
return isSame;
```

如上代码中，我们可以看出使用的遍历方式，左子树左右中，右子树右左中，所以我把这个遍历顺序也称之为“后序遍历”（尽管不是严格的后序遍历）。

**完整代码**

~~~ java
class Solution {
    public boolean isSymmetric(TreeNode root) {

//         如果只有一个节点，那么说明对称
        if(root == null){
            return true;
        }
         判断以root为根的子树是否是对称的
         return isSymmetricOfSubTree(root.left,root.right);
    }

    // 判断一两个节点为根的子树是否是对称的
    boolean isSymmetricOfSubTree(TreeNode root1,TreeNode root2){
        if(root1 == null && root2 != null){
            return false;
        }else if(root1 != null && root2 == null){
            return false;
        }else if(root1 == null && root2 == null){
            return true;
        }else if(root1.val != root2.val){
            return false;
        }
        boolean a=isSymmetricOfSubTree(root1.left, root2.right);
        boolean b=isSymmetricOfSubTree(root1.right, root2.left);
        return a&&b;
    }
}
~~~

**层次遍历**

层次遍历需要注意一点的就是先入左子树的左孩子节点，然后是右子树的右孩子节点，然后是左子树的右孩子，右子树的左孩子节点，因为我们需要判断是否对称，和下面一题相同的树分开。

**完整代码**

~~~ java
class Solution {
    public boolean isSymmetric(TreeNode root) {

//         如果只有一个节点，那么说明对称
        if(root == null){
            return true;
        }
        return isSymmetricBfs(root);

    }

// 使用bfs遍历
    boolean isSymmetricBfs(TreeNode root){

        if (root == null) {
            return true;
   
        }
        // 声明队列
        Queue<TreeNode> q=new LinkedList<>();
        q.add(root.left);
        q.add(root.right);

        while(!q.isEmpty()){
            TreeNode left=q.poll();
            TreeNode right=q.poll();
            // 判断当前左右节点值是否相等
           if((left != null && right == null)||(left == null && right != null)||(left.val != right.val)){
               return false;
           }
            if(left != null && right != null){
                continue;
            }

            q.add(left.left);
            q.add(right.right);
            q.add(left.right);
            q.add(right.left);
        }
        return true;
     
    }
}
~~~

### 相同的树

**题目描述**

![1635904392442](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/03/095312-385748.png)

**思路**
对上面对称二叉树中，我们讲到对于二叉树是否对称，要比较的是根节点的左子树与右子树是不是相互翻转的，理解这一点就知道了其实我们要比较的是两个树（这两个树是根节点的左右子树），所以在递归遍历的过程中，也是要同时遍历两棵树。

理解这一本质之后，就会发现，求二叉树是否对称，和求二叉树是否相同几乎是同一道题目。

递归三部曲中：

**确定递归函数的参数和返回值**

- 我们要比较的是两个树是否是相互相同的，参数也就是两个树的根节点。

- 返回值自然是bool类型。

> 在写递归算法中，我们通常先搞清楚如果树右一个节点的话，我们如何判断，然后所有节点依次递归即可。

代码如下：

~~~ java
bool compare(TreeNode* tree1, TreeNode* tree2)
~~~

分析过程同101.对称二叉树。

**确定终止条件**

- 要比较两个节点数值相不相同，首先要把两个节点为空的情况弄清楚！否则后面比较数值的时候就会操作空指针了。

现在我们先假设两棵树都有一个节点，来分析一下我们如何判断两棵树是否相同，假设两棵树的根节点是`tree1`和`tree2`：

- `tree1`为空，`tree2`不为空，不对称，`return false`
- `tree1`不为空，`tree2`为空，不对称` return false`
- `tree1`，`tree2`都为空，对称，返回`true`
- `tree1`、`tree2`都不为空，比较节点数值，不相同就`return false`
  - 此时`tree1`、`tree2`节点不为空，且数值也不相同的情况我们也处理了。

通过上面分析，也就是当两棵树都有一个节点的时候，需要上面5步的判断，所以很容易iu可以写出我们的递归出口条件：

~~~ java
if (tree1 == NULL && tree2 != NULL) return false;
else if (tree1 != NULL && tree2 == NULL) return false;
else if (tree1 == NULL && tree2 == NULL) return true;
else if (tree1->val != tree2->val) return false; // 注意这里我没有使用else
~~~

**确定单层递归的逻辑**

- 比较二叉树是否相同 ：传入的是tree1的左孩子，tree2的左孩子。
- 如果左右都相同就返回true ，有一侧不相同就返回false 。

~~~ java
bool left = compare(tree1->left, tree2->left);   // 左子树：左、 右子树：左
bool right = compare(tree1->right, tree2->right);  // 左子树：右、 右子树：右
bool isSame = left && right;                    // 左子树：中、 右子树：中（逻辑处理）
return isSame;
~~~

注意和上面的对称二叉树区分开。

**完整代码**

~~~ java
class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {
        return isSame(p, q);
    }

    // 使用递归的解法
    boolean isSame(TreeNode root1,TreeNode root2){
        if(root1 == null && root2 != null){
            return false;
        }else if(root1 != null && root2 == null){
            return false;
        }else if(root1 == null && root2 == null){
            return true;
        }else if(root1.val != root2.val){
            return false;
        }
        boolean b1=isSame(root1.left, root2.left);
        boolean b2=isSame(root1.right, root2.right);
        return b1&&b2;
    }
}
~~~

当然，对于本题目我们还可以考虑广度优先遍历，相同的树，无非就是保证下面两个条件：

- 树的结构一阿姨那个
- 节点的值一样

那我们思考如何才能够保证树的结构一样呢？这里可以使用层次遍历去访问一遍所有的节点，某个节点为空的话，我们使用null值代替，这样，对两棵树进行层次遍历一遍，就可以访问到所有的空值节点和非空值节点，然后判断一遍各个节点是或否值一样即可。

**完整代码**

~~~ java
class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {

        List<Integer> l1=new ArrayList<>();
        List<Integer> l2=new ArrayList<>();
        bfsOrder(p, l1);
        bfsOrder(q, l2);
        if(l1.size() != l2.size()){
            return false;
        }
        for(int i=0;i<l1.size();i++){
            if(l1.get(i) != l2.get(i)){
                return false;
            }
        }
        return true;
    }

    // 使用层次遍历
    void bfsOrder(TreeNode root,List<Integer> res){
        if (root == null) 
            return ;
       //利用队列进行层次遍历
       Queue<TreeNode> queue = new LinkedList<>();
       //第一层
       queue.add(root);
       while (!queue.isEmpty()){
           //记录每一层的个数
           int size = queue.size();
           for (int i = 0; i < size; i++){
               TreeNode tmp = queue.poll();
               if(tmp == null){
                   res.add(null);
                   continue;
               }else{
                   res.add(tmp.val);
               }       
                queue.add(tmp.left);            
                queue.add(tmp.right);                 
           }
       }
    }
}
~~~

**其他版本**

~~~ java
// 迭代法
class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {
        if(p == null && q == null) return true;
        if(p == null || q == null) return false;
        Queue<TreeNode> que= new LinkedList<TreeNode>();
        que.offer(p);
        que.offer(q);
        while(!que.isEmpty()){
            TreeNode leftNode = que.poll();
            TreeNode rightNode = que.poll();
            if(leftNode == null && rightNode == null) continue;
            if(leftNode == null || rightNode== null || leftNode.val != rightNode.val) return false;
            que.offer(leftNode.left);
            que.offer(rightNode.left);
            que.offer(leftNode.right);
            que.offer(rightNode.right);
        }
        return true;
    }
}
~~~

