## 剑指 Offer 17. 打印从1到最大的n位数

### [剑指 Offer 17. 打印从1到最大的n位数](https://leetcode-cn.com/problems/da-yin-cong-1dao-zui-da-de-nwei-shu-lcof/)

1. 将1~9加入队列。
2. 对队列中所有元素按队列顺序取出，并加入答案。同时，若提取的字符串长度小于n，那么就在它的最末尾补充0~9，依次加入队列。
3. 重复步骤2，直至队列为空。 返回答案。

**完整代码**

~~~java
class Solution {
    public int[] printNumbers(int n) {
        int[] ans = new int[(int)(Math.pow(10, n)) - 1];
        Queue<String> q = new LinkedList<>();
        //将1~9加入队列
        for (int i = 1; i <= 9; i++){
            q.offer(String.valueOf(i));
        }
        int length = 1;
        int index = 0;
        while (!q.isEmpty()){
            int size = q.size();
            for (int i = 0; i < size; i++){
                 //将队列中的元素依次取出并加入答案
                String str = q.poll();
                ans[index++] = Integer.parseInt(str);
                 //若当前元素长度不够n，则在末尾补充0~9，继续加入队列
                if (str.length() < n){
                    for (int j = 0; j <= 9; j++){
                        q.offer(str + j);
                    }
                }
            }
        }
        return ans;
    }
}
~~~

