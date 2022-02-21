## 剑指 Offer 16. 数值的整数次方

### [剑指 Offer 16. 数值的整数次方](https://leetcode-cn.com/problems/shu-zhi-de-zheng-shu-ci-fang-lcof/)

### 暴力解决

题目并没有说考虑大整数问题，所以我们可以使用暴力法解决，首先判断x,n和0的大小，然后针对不同的情况，计算不同的结果，其中计算次方使用的式循环。

缺点式可读性不是很好，需要考虑情况很多。

**完整代码**

~~~ java
class Solution {
    public double myPow(double x, int n) {

        return myPow_A(x,n);
    }

    boolean flag = false;

    public double myPow_A(double x, int n){

       flag = false;
       if( x == 0 && n<0){
           flag = true;
           return 0.0;
       }
       if(x == 1){
           return 1;
       }
       if(x == -1){
           if(n%2 == 0){
               return 1;
           }else{
               return -1;
           }
       }
        if(n == -2147483648){
            return 0.0;
        }

       if(n == 0){
           return 1.0;
       }else if(n <0){
           int absExponent = Math.abs(n);
           if(x>0){
            return 1/compute(x,absExponent);
           }else{
               if(absExponent%2 == 0){
                   return  1/compute(x,absExponent);
               }else{
                return  -1/compute(x,absExponent);
               }
           }

        }else if( n > 0){
            if(x < 0){
                x = Math.abs(x);
                if(n %2 == 0){
                    return compute(x,n);
                }else{
                    return -compute(x,n);
                }

            }else if(x>0){
                return compute(x,n);
            }
        }
        return 0.0;
    }

    double compute(double x,int n){
        double res = 1.0;
        for(int i=0;i<n;i++){
            res *= x;
        }
        return res;
    }

}
~~~

**解法二**

~~~java
    double myPow_A(double x,int b){

        if(x== 0){

            return 1.0;
        }
        double ans = 1.0;
        long n=b;
        //这一段是在快速幂的基础上额外新增的求负指数的快速幂的方法(其实也就相当于求（1/x）的快速幂)
        if(n<0){
            x=1/x;
            n=-n;
        }
        while(n!=0){
            if(n%2 ==1){
                //不需要再对ans赋值的原因是最终总会达到n=1的时候，然后这时x就赋值给了ans
                ans = ans*x;
            }
            n/=2;
            x*=x;
        }
        return ans;
    }
~~~

