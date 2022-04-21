## [剑指 Offer 37. 序列化二叉树](https://leetcode-cn.com/problems/xu-lie-hua-er-cha-shu-lcof/)

### 层次遍历序列化

~~~java
public class Codec {

    // Encodes a tree to a single string.
    public String serialize(TreeNode root) {
        
        if(root == null){
            return "";
        }
        StringBuilder sb = new StringBuilder();
        Queue<TreeNode> queue = new LinkedList();
        queue.offer(root);
        while(!queue.isEmpty()){
            int  sz = queue.size();
            // 抛出队列头部元素
            TreeNode node = queue.poll();
            if(node == null){
                sb.append("null").append(",");
                continue;
            }
            sb.append(node.val).append(",");
            queue.offer(node.left);
            queue.offer(node.right);
        }
        return sb.toString();
    }

    // Decodes your encoded data to tree.
    public TreeNode deserialize(String data) {

        int sz = data.length();
        if(sz == 0){
            return null;
        }
        String []words = data.split(",");
        TreeNode root = new TreeNode(Integer.parseInt(words[0]));
        // 队列
        Queue<TreeNode> queue = new LinkedList();
        // 根节点入队列
        queue.offer(root);
        int i=1;
        while(i < words.length){
                        // 抛出父节点
            TreeNode node = queue.poll();
            String left = words[i++];
            if(!left.equals("null")){
                node.left = new TreeNode(Integer.parseInt(left));
                queue.offer(node.left);
            }else{
                node.left = null;
            }
            String right = words[i++];
            if(!right.equals("null")){
                node.right = new TreeNode(Integer.parseInt(right));
                queue.offer(node.right);
            }else{
                node.right = null;
            }
        }
        return root;
    }
}

~~~

