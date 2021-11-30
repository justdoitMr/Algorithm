## 剑指 Offer 49. 丑数

### [剑指 Offer 49. 丑数](https://leetcode-cn.com/problems/chou-shu-lcof/)

### 枚举法

此方法会超时

~~~ java
class Solution {
    public int nthUglyNumber(int n) {

        return nthUglyNumber_A(n);

    }

    public int nthUglyNumber_A(int n) {

        int number=0;
        int num = 0;
        
        while(num < n){
             // 如果当前数是丑数
            number++;
            if(isUglyNum(number)){
                num++;
            }

        }
        return number;
    }

    public boolean isUglyNum(int num){

        while(num % 2 == 0){
            num /=2;
        }
        while(num % 3 == 0){
            num /=3;
        }
        while(num % 5 == 0){
            num /=5;
        }
        if(num == 1){
            return true;
        }
        return false;
    }
}
~~~

### 使用辅助数组

考虑到上面一种方法，对每一个数我们都需要判断，所以时间效率很低，那么我们重新明确丑数的定义，丑数的因子必须是2，3，5，也就是说我们当前求的丑数，必须是一个丑数乘以2，或者3或者5获得的，

也就是说，我们在判断一个数字是不是丑数的时候，只和之前的丑数有关系，和非丑数没有关系，所以我们使用一个数组老保存之前求出来的丑数。那么在求第i个丑数的时候，我们已经直到第i个丑数是由之前的丑数乘以2或者3或者5得到的，

~~~ java
 // 使用辅助数组的方法
     public int nthUglyNumber_B(int n) {

        int []ugluDp=new int [n];
        ugluDp[0]=1;

        int ugly2=0;
        int ugly3=0;
        int ugly5=0;
       int index = 1;
       while(index< n){

//             更新丑数数组
           ugluDp[index]=Math.min(ugluDp[ugly2]*2,ugluDp[ugly3]*3);
           ugluDp[index]=Math.min(ugluDp[ugly5]*5,ugluDp[index]);
           while(ugluDp[ugly2] * 2 <= ugluDp[index]){
               ugly2++;
           }
           while(ugluDp[ugly3] * 3 <= ugluDp[index]){
               ugly3++;
           }
           while(ugluDp[ugly5] * 5 <= ugluDp[index]){
               ugly5++;
           }
           index++;
       }

       return ugluDp[index-1];
    }
~~~

