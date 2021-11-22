
<!-- TOC -->

- [剑指 Offer 18. 删除链表的节点](#剑指-offer-18-删除链表的节点)
  - [剑指 Offer 18. 删除链表的节点](#剑指-offer-18-删除链表的节点-1)
  - [单指针](#单指针)

<!-- /TOC -->
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

### 单指针

1. 首先判断是否删除的节点为第一个，是的话直接返回就行
2. 如果删除的不是第一个，那么就遍历链表。每次遍历的时候我们都要判断一下下一个节点的值是否为要删除的节点的值：如果是的话，将当前节点指向待删除节点的下一个节点，这样子就成功删除了；否则就继续遍历

**完整代码**

~~~ java
public ListNode deleteNode(ListNode head, int val) {
        ListNode p = head;

        // 例外情况，如果删除的是第一个节点，那就直接返回第一个节点
        if (p.val == val) {
            return head.next;
        }


        while (p.next != null) {
            if (p.next.val == val) {
                // 当前节点指向待删除节点的下一个节点，这样子就成功删除了
                p.next = p.next.next;
                return head;
            }
            p = p.next;
        }

        return head;
    }
~~~

前两种思路都是从待删除节点的前一个节点入手开始删除。

时间复杂度是o(n)。

第二种思路不需要使用额外的指针去指向待删除节点的上一个节点，使用一个指针，遍历链表，直到找到待删除的节点为止，然后把待删除节点的下一个节点值覆盖待删除节点处的值，然后删除待删除节点的下一个节点即可。

但是假如我们的链表只有一个节点并且该节点值等于待删除节点值，或者说我们待删除的节点是最后一个情况怎么办？ 这需要我们另外进行考虑。

也就是先找到待删除节点的前一个节点，然后在删除。

使用这种方法的好处是平均时间复杂度是o(1)。

对于n-1个非尾节点而言，我们可以在o(1)时间内删除节点，但是对于尾节点eryan-，我们仍然需要遍历链表，找到待删除节点的前一个节点，所以总的平均之间复杂度是o(((n-1)*o(1)+o(n)))/n，最后还是o(1)。