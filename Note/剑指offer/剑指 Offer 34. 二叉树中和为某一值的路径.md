## 剑指 Offer 34. 二叉树中和为某一值的路径

### [剑指 Offer 34. 二叉树中和为某一值的路径](https://leetcode-cn.com/problems/er-cha-shu-zhong-he-wei-mou-yi-zhi-de-lu-jing-lcof/)

### 回溯法

#### **带剪枝的回溯法**

~~~ java
List<List<Integer>> res = new ArrayList();
        public List<List<Integer>> pathSum(TreeNode root, int target) {
    
            ArrayList<Integer> temp = new ArrayList();
    
            pathSum_A(root,target,temp);
            return res;
    
        }
    
        public void pathSum_A(TreeNode root, int target,ArrayList<Integer>temp) {

            if(root == null){
                return ;
            }
             temp.add(root.val);
             target = target-root.val;
            if(root.left == null && root.right == null && target == 0){
    
                res.add(new ArrayList(temp));
                temp.remove(temp.size()-1);
                // 在这里使用return相当于做剪枝
                // 这里使用return相当于做剪枝，所以在这里要多做一次回溯操作
                return;
            }
           
            pathSum_A(root.left,target,temp);
            pathSum_A(root.right,target,temp);
            // 回溯
            target +=root.val;
            temp.remove(temp.size()-1);
    
    
        }
~~~

#### **不带剪枝的回溯**

~~~ java
class Solution {
    List<List<Integer>> res = new ArrayList();
    public List<List<Integer>> pathSum(TreeNode root, int target) {

        ArrayList<Integer> temp = new ArrayList();

        pathSum_A(root,target,temp);
        return res;

    }

    public void pathSum_A(TreeNode root, int target,ArrayList<Integer>temp) {

            if(root == null){
                return ;
            }
             temp.add(root.val);
             target = target-root.val;
            if(root.left == null && root.right == null && target == 0){
                res.add(new ArrayList(temp));
            }
           
            pathSum_A(root.left,target,temp);
            pathSum_A(root.right,target,temp);
            // 回溯
            target +=root.val;
            temp.remove(temp.size()-1);
    
        }
}
~~~

#### **使用链表**

~~~ java
    LinkedList<List<Integer>> res = new LinkedList<>();
    LinkedList<Integer> path = new LinkedList<>(); 
    public List<List<Integer>> pathSum(TreeNode root, int sum) {
        recur(root, sum);
        return res;
    }
    void recur(TreeNode root, int tar) {
        if(root == null) return;
        path.add(root.val);
        tar -= root.val;
        if(tar == 0 && root.left == null && root.right == null)
            res.add(new LinkedList(path));
        recur(root.left, tar);
        recur(root.right, tar);
        path.removeLast();
    }

~~~

### 模板写法

~~~java
class Solution {
    public List<List<Integer>> pathSum(TreeNode root, int target) {
        List<List<Integer>> res = new ArrayList<>();
        if(root==null){
            return res;
        }
        LinkedList<Integer> tmp = new LinkedList<>();
        dfs(root,target,res,tmp);
        return res;
    }
    public void dfs(TreeNode root, int target, List<List<Integer>> res, LinkedList<Integer> tmp){
        
        if(root.left==null&&root.right==null){
            if(target==root.val){
                tmp.add(root.val);
                res.add(new ArrayList<Integer>(tmp));
                tmp.pollLast();
            }
            return;
        }
        tmp.add(root.val);
        if(root.left!=null) dfs(root.left,target-root.val,res,tmp);
        if(root.right!=null) dfs(root.right,target-root.val,res,tmp);
        tmp.pollLast();
    }
}
~~~

