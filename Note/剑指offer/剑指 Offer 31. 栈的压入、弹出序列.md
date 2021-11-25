## 剑指 Offer 31. 栈的压入、弹出序列

### [剑指 Offer 31. 栈的压入、弹出序列](https://leetcode-cn.com/problems/zhan-de-ya-ru-dan-chu-xu-lie-lcof/)

### 思路一

- 我们使用一个栈stack来模拟栈的push和pop操作：
- 首先肯定要将所有元素一个个入栈，我们可以再入栈的时候根据popped判断是否需要出栈：如果当前栈顶元素等于popped[index]的元素，那么就出栈，直到不等于为止。
- 如果最后遍历一次栈结束后了，我们看看stack是否为空：若为空的话，说明弹出栈的顺序符合条件，刚刚好全部弹出了；如果不为空，说明某个位置不符合弹出条件，然后就一直卡住不能弹出。
- 最后只需要判断stack栈是否为空就知道栈的弹出顺序是否符合条件了

**完整代码**

~~~ java
class Solution {
    public boolean validateStackSequences(int[] pushed, int[] popped) {

        return validateStackSequences_A(pushed,popped);

    }

     public boolean validateStackSequences_A(int[] pushed, int[] popped) {

        // 用于模拟的栈
        LinkedList<Integer> stack = new LinkedList<>();
        // 用于popped数组的索引
        int index = 0;

        // 进行模拟
        for (int i = 0; i < pushed.length; i++) {
            // 每次都入栈一个元素
            stack.push(pushed[i]);
            // 查看栈顶的元素和popped的元素是否一样，一样的话，我们就模拟出栈
            // 这里index不能越界，且模拟栈不能为空：这样才能进行比较
            while (!stack.isEmpty() && popped[index] == stack.peek()) {
                stack.pop();
                index++;
            }
        }
        // 如果最终模拟的栈是空的，说明符合弹出顺序
        return stack.isEmpty();

    }
}
~~~

