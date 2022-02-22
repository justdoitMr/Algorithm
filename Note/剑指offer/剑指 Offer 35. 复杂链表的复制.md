## 剑指 Offer 35. 复杂链表的复制

### [剑指 Offer 35. 复杂链表的复制](https://leetcode-cn.com/problems/fu-za-lian-biao-de-fu-zhi-lcof/)

在原链表每个结点后面新建一个一模一样的结点，然后拆分链表；

1. 第一次遍历原链表时，在每个结点后新建值相同的结点，形式如:1->1'->2->2'；
2. 第二次遍历原链表时，修改每个新结点的random指向；
3. 第三次遍历原链表时，把新结点逐个拆下构成新链表，并恢复原链表；

**核心代码**

~~~java
    public Node copyRandomList_A(Node head){

        if(head == null){
            return null;
        }

        // 首先再原始链表的基础上进行复制操作
        Node p = head;
        while(p!= null){
            Node temp = new Node(p.val);
            temp.next = p.next;
            p.next = temp;
            p=temp.next;
        }

        // 修正random的指向即可
        p = head;
        while(p != null){

            if(p.random != null){
                p.next.random = p.random.next;
            }
            p = p.next.next;
        }

        // 删除head链表即可

       Node newHead = head.next;//保存新链表的头节点
       p = newHead;//新链表的工作指针
       Node cur = head;
        while(p.next !=null){
            // 重新连接原始链表
            cur.next = cur.next.next;
            // 重新连接新的链表
            p.next = p.next.next;
            cur = cur.next;
            p = p.next;
        }
        cur.next = null;

        return newHead;

    }
~~~

