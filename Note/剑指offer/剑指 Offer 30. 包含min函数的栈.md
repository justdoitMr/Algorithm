## 剑指 Offer 30. 包含min函数的栈

### [剑指 Offer 30. 包含min函数的栈](https://leetcode-cn.com/problems/bao-han-minhan-shu-de-zhan-lcof/)

使用两个栈，stack栈存放普通的元素，min栈存放维护一个最小元素的集合，当每次插入一个元素的时候，都和min栈顶的元素比较，如果当前元素小于栈顶元素，那么就入栈，如果大于，就不入栈。

**完整代码**

~~~java
class MinStack {

    Stack<Integer> stack;
    Stack<Integer> min;
    /** initialize your data structure here. */
    public MinStack() {
        stack = new Stack();
        min = new Stack();
    }
    
    public void push(int x) {
        stack.push(x);
        if(!min.isEmpty()){
            if(min.peek()>=x){
                min.push(x);
            }
        }else{
            min.push(x);
        }

    }
    // 抛出栈顶元素
    public void pop() {
        if(min.peek() == stack.peek()){
            min.pop();
            stack.pop();
        }else{
            stack.pop();
        }

    }
    
    public int top() {
        // 返回栈顶元素
        return stack.peek();
    }
    
    public int min() {
        if(!min.isEmpty()){
            return min.peek();
        }
        return 0;
    }
}
~~~

