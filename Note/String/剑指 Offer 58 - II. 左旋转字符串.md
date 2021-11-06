## 剑指 Offer 58 - II. 左旋转字符串

[剑指 Offer 58 - II. 左旋转字符串](https://leetcode-cn.com/problems/zuo-xuan-zhuan-zi-fu-chuan-lcof/)

**思路一**

使用字符串拼接，首先截取前n个字符，然后删除字符串的前n个字符，拼接到末尾。

**完整代码**

~~~ java
class Solution {
    public String reverseLeftWords(String s, int n) {

        return reverseLeftWords_A(s,n);

    }

    String reverseLeftWords_A(String s,int n){
        String subStr=s.substring(0,n);
        StringBuilder sb=new StringBuilder(s);
        sb.delete(0,n);
        return sb.append(subStr).toString();
    }
}
~~~

**思路二**

原地反转

- 先将前n个进行翻转，再将后n个进行翻转，最后再整体翻转一遍
- 我们把他看成两个部分，然后对每个部分都是一个整体，内部不需要翻转，因此我们可以把这题可以看作是剑指 Offer 58 - I. 翻转单词顺序只有两个单词的情况

> a—b–c–d–e、n=2
>
> 1. 首先将前两个字符反转，后三个字符反转
>
> b–a–e–d–c
>
> 2. 将整体在反转一遍
>
> c–d–e–a–b

**完整代码**

~~~ java
class Solution {
    public String reverseLeftWords(String s, int n) {

        return reverseLeftWords_B(s,n);

    }

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
}
~~~

