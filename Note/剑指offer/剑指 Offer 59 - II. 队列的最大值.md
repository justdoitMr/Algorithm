## 剑指 Offer 59 - II. 队列的最大值

### [剑指 Offer 59 - II. 队列的最大值](https://leetcode-cn.com/problems/dui-lie-de-zui-da-zhi-lcof/)

### 单调队列

先说一下什么是单调队列，就是队列中的元素，单调递增或者是单调递减。

~~~ java
class MaxQueue {

    // 存储所有的元素
   private Deque<Integer> queue;
//    存储单调递减的元素
    private Deque<Integer> help;

    public MaxQueue() {
        queue = new ArrayDeque<>();
        help = new ArrayDeque<>();
    }
    
    public int max_value() {
        return queue.isEmpty() ? -1 : help.peek();
    }
    
    public void push_back(int value) {
        // 元素入正常队列
        // 把当前元素放入单调队列合适位置
        queue.offer(value);
        while(!help.isEmpty() && value > help.peekLast()) {
            help.pollLast();
        }
        help.offer(value);
    }
    
    //抛出队列首元素
    public int pop_front() {
        if(queue.isEmpty()) {
            return -1;
        }
        int val = queue.pop();
        if(help.peek() == val) {
            help.pop();
        }
        return val;
    }
}

/**
 * Your MaxQueue object will be instantiated and called as such:
 * MaxQueue obj = new MaxQueue();
 * int param_1 = obj.max_value();
 * obj.push_back(value);
 * int param_3 = obj.pop_front();
 */
~~~

