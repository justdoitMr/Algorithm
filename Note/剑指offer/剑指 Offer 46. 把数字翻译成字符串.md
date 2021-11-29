## 剑指 Offer 46. 把数字翻译成字符串

### [剑指 Offer 46. 把数字翻译成字符串](https://leetcode-cn.com/problems/ba-shu-zi-fan-yi-cheng-zi-fu-chuan-lcof/)

### 字符串动态规划

这道题目和青蛙跳台阶题目很类似，





### 完整代码

~~~ java
class Solution {
    public int translateNum(int num) {

        return translateNum_A(num);

    }

     public int translateNum_A(int num) {

         if(num < 0){
             return -1;
         }
        //  将数字转换为字符串，获取每一位
         String str=String.valueOf(num);
        //  声明一个dp数组
        int [] dp = new int[str.length()+1];

        // 初始化dp数组
        // dp数组表示，到第i位位置，有多少种翻译方法
        dp[0]=1;
        dp[1]=1;

        for(int i=2;i<=str.length();i++){

            String temp = str.substring(i-2,i);

            if(temp.compareTo("10")>=0 && temp.compareTo("25")<=0){
                dp[i]=dp[i-1]+dp[i-2];
            }else{
                dp[i]=dp[i-1];
            }
        }

        return dp[str.length()];
     }   
}
~~~

