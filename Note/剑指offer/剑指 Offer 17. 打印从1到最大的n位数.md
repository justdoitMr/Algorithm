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

### 使用回溯

排列解法

在数字很大的情况下，哪怕long类型也无法承载，那必须要用字符串保存。

对于本题其实就是对数字0~9的全排列，从1位数0~9的全排列到n位数0~9的全排列，其中要注意的是数字开头不应该有0。

简单提一下全排列，比如对于数字1，2，3的全排列是:

> 123, 132, 213, 231, 312, 321
> 为了能够测试通过，最后把字符串形式变成了int形式，其实应该返回字符串数组

以下是具体步骤

1. 为了避免数字开头出现0，先把首位first固定，first取值范围为1~9
2. 用digit表示要生成的数字的位数，本题要从1位数一直生成到n位数，对每种数字的位数都生成一下首位，所以有个双重for循环
3. 生成首位之后进入递归生成剩下的digit - 1位数，从0~9中取值
4. 递归的中止条件为已经生成了digit位的数字，即index == digit，将此时的数num转为int加到结果res中

~~~java
class Solution {
    
    int[] res;
    int count = 0;
    public int[] printNumbers(int n) {

        // return printNumbers_A(n);

        res = new int[(int)Math.pow(10, n) - 1];
        for(int digit = 1; digit < n + 1; digit++){
            for(char first = '1'; first <= '9'; first++){
                char[] num = new char[digit];
                num[0] = first;
                dfs(1, num, digit);
            }
        }
        return res;


    }

    private void dfs(int index, char[] num, int digit){

        // 剪枝操作
        if(index > digit){
            return;
        }
        if(index == digit){
            res[count++] = Integer.parseInt(String.valueOf(num));
            return;
        }
        for(char i = '0'; i <= '9'; i++){
            num[index] = i;
            dfs(index + 1, num, digit);
        }
    }
}
~~~

