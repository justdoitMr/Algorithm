## 剑指 Offer 05. 替换空格

### **题目描述**

[剑指 Offer 05. 替换空格](https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/)

### **使用StringBuilder**

第一种思路是使用`StringBuilder`进行拼接，以空间换取时间，但是还需要对字符串进行遍历操作，所以时间复杂度是o(n)。

**完整代码**

~~~ java
class Solution {
    public String replaceSpace(String s) {

        return replaceSpace_A(s);
        
    }

    // 使用StringBuilder
    public Strign replaceSpace_A(String s){
        StringBuilder sb = new StringBuilder();

        for(int i=0;i< s.length();i++){
            if(s.charAt(i) != ' '){
                char c=s.charAt(i);
                sb.append(c);
            }else{
                sb.append("%20");
            }
        }
        return sb.toString();
    }
}
~~~

时间复杂度是：o：(n)

空间复杂度是：o(n)

### 使用双指针

可以首先遍历字符串，记录空字符的个数，然后对原始数组婧扩容操作，然后从后先前遍历数组，把所有的字符向后移动，直到遇到空字符添加%20即可，时间复杂度是o(n),空间复杂度是o(1)

**完整代码**

~~~ java
 //o(n)时间复杂度的算法
    public String replaceSpace_B(String s) {
         int count = 0; // 统计空格的个数
        int sOldSize = s.length();
        for (int i = 0; i < sOldSize; i++) {
            if (s.charAt(i) == ' ') {
                count++;
            }
        }

        char ch[]=new char[sOldSize+count*2];
        int j=ch.length-1;

        for(int i= sOldSize-1;i>=0;i--){
            if(s.charAt(i) != ' '){
                ch[j--]=s.charAt(i);
            }else{
                // 遇到一个空字符
                ch[j--]='0';
                ch[j--]='2';
                ch[j--]='%';
            }
        }

        // 字符数组转换为字符串
        String res =String.copyValueOf(ch);

        return res;
    }
~~~

这种方法，时间复杂度是o(n)。

> java中字符数组转换为字符串：String res=String.copyValueOf(ch)

### 技巧

在合并两个数组，包括字符串的时候，如果从前向后复制每一个数字或者字符则需要移动数字或者字符多次，所以我们能否考虑从后向前移动，就能减少移动的次数，降低时间复杂度。