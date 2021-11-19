## 剑指 Offer 10- II. 青蛙跳台阶问题

### [剑指 Offer 10- II. 青蛙跳台阶问题](https://leetcode-cn.com/problems/qing-wa-tiao-tai-jie-wen-ti-lcof/)

![1637288814589](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/19/102655-816079.png)

![1637288834609](https://tprzfbucket.oss-cn-beijing.aliyuncs.com/hadoop/202111/19/102715-357811.png)

![1637288860460](C:\Users\MrR\AppData\Roaming\Typora\typora-user-images\1637288860460.png)

### 动态规划

~~~ java
class Solution {
    public int numWays(int n) {
        final int MOD = 1000000007;
        if(n ==0){
            return 1;
        }
            if(n ==1){
                return 1;
            }
            if(n == 2){
                return 2;
            }
        
        int num1=1;
        int num2=2;
        int res=0;
        for(int i=3;i<=n;i++){
            res = (num1+num2)%MOD;
            num1=num2;
            num2=res; 
            
        }
            return res;
    }
}
~~~

