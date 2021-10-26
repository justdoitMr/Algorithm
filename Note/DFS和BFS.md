# DFS和BFS

深度优先遍历（Depth First Search, 简称 DFS） 与广度优先遍历（Breath First Search）是图论中两种⾮常重要的算法，⽣生产上⼴广泛⽤用于拓拓扑排序，寻路路（⾛走迷宫），搜索引擎，爬⾍虫等，也频繁出现在leetcode，⾼高频⾯面试题中。

## 深度优先遍历（DFS）

深度优先遍历主要思路是从图中一个未访问的顶点 V 开始，沿着一条路⼀直走到底，然后从这条路尽头
的节点回退到上一个节点，再从另一条路开始⾛到底...，不断递归重复此过程，直到所有的顶点都遍历
完成，它的特点是不撞南墙不回头，先走完⼀条路，再换一条路继续⾛。

树是图的⼀种特例例（连通无环的图就是树），接下来我们来看看树用深度优先遍历该怎么遍历。

![1635143973912](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/143934-460115.png)

1. 我们从根节点 1 开始遍历，它相邻的节点有 2，3，4，先遍历节点 2，再遍历 2 的子节点 5，然后
   再遍历 5 的子节点 9。

![1635144082796](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/144123-659937.png)

2. 上图中⼀条路已经⾛到底了（9是叶子节点，再无可遍历的节点），此时就从 9 回退到上一个节点
3. 看下节点 5 是否还有除 9 以外的节点，没有继续回退到 2，2 也没有除 5 以外的节点，回退到 1，1
   有除 2 以外的节点 3，所以从节点 3 开始进行深度优先遍历，如下：

![1635144194197](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/144314-199079.png)

4. 同理从 10 开始往上回溯到 6, 6 没有除 10 以外的子节点，再往上回溯，发现 3 有除 6 以外的子点
   7，所以此时会遍历 7

![1635144236688](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/144357-975864.png)

5. 从 7 往上回溯到 3， 1，发现 1 还有节点 4 未遍历，所以此时沿着 4， 8 进行遍历,这样就遍历完成
   了

**完整节点遍历顺序如下**

![1635144317508](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/144518-435097.png)

相信大家看到以上的遍历不难发现这就是树的前序遍历,实际上不管是前序遍历，还是中序遍历，亦或是
后序遍历，都属于深度优先遍历。

那么深度优先遍历该怎么实现呢，有递归和⾮递归两种表现形式，接下来我们以二叉树为例来看下如何
分别⽤递归和⾮递归来实现深度优先遍历。

**递归实现**

递归实现比较简单，由于是前序遍历，所以我们依次遍历当前节点，左节点，右节点即可，对于左右节
点来说，依次遍历它们的左右节点即可，依此不断递归下去，直到叶节点（递归终⽌止条件），代码如下

~~~ java
public class Solution {
  private static class Node {
    /**
    * 节点值
    */
    public int value;
    /**
    * 左节点
    */
    public Node left;
    /**
    * 右节点
    */
    public Node right;
    public Node(int value, Node left, Node right) {
      this.value = value;
      this.left = left;
      this.right = right;
  	}
	}
  public static void dfs(Node treeNode) {
    if (treeNode == null) {
    	return;
    }
    // 遍历节点
    process(treeNode)
    // 遍历左节点
    dfs(treeNode.left);
    // 遍历右节点
    dfs(treeNode.right);
  }
}
~~~

递归的表达性很好，也很容易理解，不过如果层级过深，很容易导致栈溢出。所以我们重点看下非递归
实现。

**非递归实现**

仔细观察深度优先遍历的特点，对二叉树来说，由于是先序遍历（先遍历当前节点，再遍历左节点，再
遍历右节点），所以我们有如下思路：

1. 对于每个节点来说，先遍历当前节点，然后把右节点压栈，再压左节点（这样弹栈的时候会先拿到
   左节点遍历，符合深度优先遍历要求）

2. 弹栈，拿到栈顶的节点，如果节点不为空，重复步骤 1， 如果为空，结束遍历。

我们以下二叉树为例来看下如何用栈来实现 DFS。

![1635144791581](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/145312-153401.png)

整体思路还是⽐较清晰的，使用栈来将要遍历的节点压栈，然后出栈后检查此节点是否还有未遍历的节
点，有的话压栈，没有的话不断回溯（出栈），有了思路，不难写出如下用栈实现的二叉树的深度优先
遍历代码:

~~~ java
class Solution {
    public List<Integer> preorderTraversal(TreeNode root) {
        // 使用深度优先遍历实现前序遍历
        List<Integer>res=new ArrayList();

        preOrderDfs(root, res);
        return res;
    }
    void preOrderDfs(TreeNode root,List<Integer> temp){
        if(root == null){
            return ;
        }
        // 声明一个栈结构
        Stack<TreeNode> s=new Stack();
        s.push(root);
        // 栈不空的话，循环出栈元素
        while(!s.isEmpty()){
            // 抛出栈顶元素并且删除
            TreeNode node=s.pop();
            temp.add(node.val);
            // 把孩子节点入栈
            if(node.right != null){
                s.push(node.right);
            }
            if(node.left != null){
                s.push(node.left);
            }
        }
    }
}
~~~

可以看到用栈实现深度优先遍历其实代码也不复杂，而且也不用担心递归那样层级过深导致的栈溢出问
题。

## 广度优先遍历(BFS)

广度优先遍历，指的是从图的一个未遍历的节点出发，先遍历这个节点的相邻节点，再依遍次历每个相
邻节点的相邻节点。

上文所述树的广度优先遍历图如下，每个节点的值即为它们的遍历顺序。所以广度优先遍历也叫层序
遍历，先遍历第一层（节点 1），再遍历第二层（节点 2，3，4），第三层（5，6，7，8），第四层
（9，10）。

![1635145677095](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/150758-242671.png)

深度优先遍历用的是栈，而广度优先遍历要用队列列来实现，我们以下图二叉树为例来看如何用队列来
进行深度优先遍历。

![1635145721717](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/150842-587140.png)

**代码实现**

~~~ java
class Solution {
    List<List<Integer>> res=new ArrayList<>();
    public List<List<Integer>> levelOrder(TreeNode root) {
    
        ArrayList<Integer> l=new ArrayList<>();
        bfsOrder(root, l);
        return res;
    }
    void bfsOrder(TreeNode root,ArrayList<Integer> temp){

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
               //把下一层的节点加进去
               if (tmp.left != null) queue.add(tmp.left);
               if (tmp.right != null) queue.add(tmp.right);
               //记录
               temp.add(tmp.val);
           }
           //一层遍历完成，添加path到res
           res.add(new ArrayList<>(temp));
           temp.clear();
       }
    }
}
~~~

## 练习

接下来我们来看看在 leetcode 中出现的⼀些使⽤用 DFS，BFS 来解题的题目:

> leetcode 104，111: 给定一个⼆叉树，找出其最大/最小深度。

![1635147142907](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/153224-545545.png)

解题思路：这题⽐较简单，只不过是深度优先遍历的一种变形，只要递归求出左右⼦树的最大/最⼩深度
即可，深度怎么求，每递归调⽤用⼀次函数，深度加一。不难写出如下代码：

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

**求最小深度**

![1635149306891](C:\Users\MrR\AppData\Roaming\Typora\typora-user-images\1635149306891.png)

**广度优先实现**

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

> leetcode 102: 给你一个二叉树，请你返回其按层序遍历得到的节点值。 （即逐层地，从左到右访
> 问所有节点）。 示例例，给定⼆叉树：[3,9,20,null,null,15,7]

![1635149622508](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202110/25/161343-826667.png)

解题思路：显然这道题是广度优先遍历的变种，只需要在广度优先遍历的过程中，把每⼀层的节点都添
加到同⼀个数组中即可，问题的关键在于遍历同一层节点前，必须先算出同一层的节点有多少，不然由
于 BFS 用的是队列列来实现的，遍历过程中会不断把左右子节点入队，不事先算出同一层节点的话，会把同一层的左右节点也加到同⼀层的节点去，这⼀点切记

~~~ java
class Solution {
    List<List<Integer>> res=new ArrayList<>();
    public List<List<Integer>> levelOrder(TreeNode root) {

      
        ArrayList<Integer> l=new ArrayList<>();
        bfsOrder(root, l);

        return res;

    }
    void bfsOrder(TreeNode root,ArrayList<Integer> temp){

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
               //把下一层的节点加进去
               if (tmp.left != null) queue.add(tmp.left);
               if (tmp.right != null) queue.add(tmp.right);
               //记录
               temp.add(tmp.val);
           }
           //一层遍历完成，添加path到res
           res.add(new ArrayList<>(temp));
           temp.clear();
       }
    }
}
~~~

这题用 BFS 是显而易⻅的，但其实也可以用 DFS， 如果在面试中能用 DFS 来处理，会是一个⽐较大的
亮点。用 DFS 怎么处理呢，我们知道， DFS 可以用递归来实现，其实只要在递归函数上加上一个「层」的变量即可，只要节点属于这一层，则把这个节点放入相当层的数组⾥里，代码如下：

