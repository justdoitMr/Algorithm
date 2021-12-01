
<!-- TOC -->

- [剑指 Offer 58 - II. 左旋转字符串](#剑指-offer-58---ii-左旋转字符串)
  - [剑指 Offer 58 - II. 左旋转字符串](#剑指-offer-58---ii-左旋转字符串-1)
  - [使用StringBuilder](#使用stringbuilder)
  - [递归反转法](#递归反转法)

<!-- /TOC -->

## 剑指 Offer 58 - II. 左旋转字符串

### [剑指 Offer 58 - II. 左旋转字符串](https://leetcode-cn.com/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/)

### 使用StringBuilder

~~~ java
String reverseLeftWords_A(String s,int n){
        String subStr=s.substring(0,n);
        StringBuilder sb=new StringBuilder(s);
        sb.delete(0,n);
        return sb.append(subStr).toString();
    }
~~~

### 递归反转法

~~~ java
String reverseLeftWords_B(String s,int n){

        // 首先将字符串转换为i数组
        char []ch=s.toCharArray();
        // 首先将前n个字符反转
        reverse(ch,0,n-1);
        // 将末尾字符进行反转
        reverse(ch,n,ch.length-1);
        
        // 反转整个字符串
        reverse(ch,0,ch.length-1);

        return String.valueOf(ch);
    }

    // 实现反转功能
    // 闭区间反转
    public void reverse(char []ch,int begin,int end){

        while(begin < end){
            char c=ch[end];
            ch[end]=ch[begin];
            ch[begin]=c;
            begin ++;
            end--;
        }

    }
~~~

