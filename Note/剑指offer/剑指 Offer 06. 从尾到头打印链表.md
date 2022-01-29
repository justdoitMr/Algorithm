## 剑指 Offer 06. 从尾到头打印链表

### [剑指 Offer 06. 从尾到头打印链表](https://leetcode-cn.com/problems/cong-wei-dao-tou-da-yin-lian-biao-lcof/)

### 使用栈

借助栈先进后出特性很容易实现。

~~~ java
 // 使用栈
    public int[] reversePrint_A(ListNode head) {

        Stack<Integer> stack = new Stack();
        ListNode p =head;
        while(p != null){
            stack.push(p.val);
            p = p.next;
        }

        int res[] = new int[stack.size()];
        if(stack.size() == 0){
            return res;
        }
        int i=0;
        while(!stack.isEmpty()){
            res[i++]=stack.pop();
        }
        return res;

    }
~~~

使用栈的时间复杂度是：o(n)

空间复杂度是：o(n),也就是递归站调用的深度。

### 使用递归

使用递归，递归让指针遍历到链表的末尾，然后从后向前输出。

因为我们是先让指针走向末尾，然后在打印，所以访问元素应该在递归后面进行。

~~~ java
class Solution {
    ArrayList<Integer> list = new ArrayList();
    public int[] reversePrint(ListNode head) {
        reversePrint_B(head);

        int []res=new int[list.size()];
        for(int i=0;i< list.size();i++){
            res[i]=list.get(i);
        }
        return res;


    }
    
    public void reversePrint_B(ListNode head) {

        if(head == null){
            return ;
        }
        reversePrint_B(head.next);
        list.add(head.val);

    }
}
~~~

时间复杂度是：o(n)