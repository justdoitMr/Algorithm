## 剑指 Offer 18. 删除链表的节点

### [剑指 Offer 18. 删除链表的节点](https://leetcode-cn.com/problems/shan-chu-lian-biao-de-jie-dian-lcof/)

1. 考虑边界条件，如果head位空，直接返回即可
2. 在做链表题目的时候，我们最好指定一个dummp节点指向头节点，这样我们对链表的操作就同意了。

**完整代码**

~~~ java
class Solution {
    public ListNode deleteNode(ListNode head, int val) {

        return deleteNode_A(head,val);

    }

    public ListNode deleteNode_A(ListNode head, int val) {

        if(head == null){
            return null;
        }
        // 定义一个dummp
        ListNode dummp = new ListNode(-1);
        dummp.next = head;
        ListNode p =head;
        ListNode q= dummp;
        while(p != null){
            if(p.val == val){
                q.next = p.next;
            }
            p = p.next;
            q=q.next;

        }
        return dummp.next;
    }
}
~~~

