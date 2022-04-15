## [剑指 Offer 59 - I. 滑动窗口的最大值](https://leetcode-cn.com/problems/hua-dong-chuang-kou-de-zui-da-zhi-lcof/)

> 单调队列：https://leetcode-cn.com/problems/hua-dong-chuang-kou-de-zui-da-zhi-lcof/solution/dong-hua-yan-shi-dan-diao-dui-lie-jian-z-unpy/

滑动窗口，重要的是维护一个窗口内最大值的队列。

**代码实现**

~~~java
    public int[] maxSlidingWindow(int[] nums, int k) {
        // 窗口个数
        int[] res = new int[nums.length - k + 1];
        LinkedList<Integer> queue = new LinkedList<>();

        // 遍历数组中元素，right表示滑动窗口右边界
        for(int right = 0; right < nums.length; right++) {
            // 如果队列不为空且当前考察元素大于等于队尾元素，则将队尾元素移除。
            // 直到，队列为空或当前考察元素小于新的队尾元素
            while (!queue.isEmpty() && nums[right] >= nums[queue.peekLast()]) {
                queue.removeLast();
            }

            // 存储元素下标
            queue.addLast(right);

            // 计算窗口左侧边界
            int left = right - k +1;
            // 当队首元素的下标小于滑动窗口左侧边界left时
            // 表示队首元素已经不再滑动窗口内，因此将其从队首移除
            if (queue.peekFirst() < left) {
                queue.removeFirst();
            }

            // 由于数组下标从0开始，因此当窗口右边界right+1大于等于窗口大小k时
            // 意味着窗口形成。此时，队首元素就是该窗口内的最大值
            if (right +1 >= k) {
                res[left] = nums[queue.peekFirst()];
            }
        }
        return res;
    }
~~~

**代码**

~~~java
class Solution {
    public int[] maxSlidingWindow(int[] nums, int k) {

        return maxSlidingWindow_A(nums,k);
    }

    public int[] maxSlidingWindow_A(int nums[],int k){

        int sz = nums.length;

        if(sz == 0){
            return new int[0];
        }
        //双端队列，队尾插入元素和删除元素
        // 队头删除元素
        LinkedList<Integer> queue = new LinkedList<Integer>();
        ArrayList<Integer> list = new ArrayList();
        // 维护左右窗口的下表
        int left =0;
        int right = 0;
        while(right < sz){

            // 判断当前元素和队列中元素的大小
            // 队列中的元素是单调递减的
            while(!queue.isEmpty() && nums[right]> nums[queue.peekLast()]){
                // 删除队列尾部元素
                queue.removeLast();
            }
            // 否则将下表入队列尾部
            queue.addLast(right);

            // 判断是否需要缩小窗口
            if(right - left+1 == k){
                int temp = nums[left];
                left++;
                list.add(nums[queue.peekFirst()]);
                // 判断队列头部的元素是否是窗口左端的元素
                if(nums[queue.peekFirst()]== temp){
                    // 如果是的话，就删除队列头部的元素
                    queue.removeFirst();
                }
            }
            // 增大窗口
            right++;
        }
        int []res = new int[list.size()];
        for(int i=0;i<list.size();i++){
            res[i] = list.get(i);
        }
        return res;
    }
}
~~~

### 双端队列的使用

~~~java
//        双端队列
        LinkedList<Integer> queue = new LinkedList<Integer>();
//        向队列尾部添加元素
        queue.addLast(111);
//        删除队列尾部的元素
        queue.removeLast();
//        从队列头部添加元素
        queue.addFirst(222);
//        从队列头部添加元素
        queue.removeFirst();
//        返回队列头部的元素
        queue.peekFirst();
//        返回队列尾部的元素
        queue.peekLast();
~~~



