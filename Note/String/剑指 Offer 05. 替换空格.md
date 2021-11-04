## 剑指 Offer 05. 替换空格

**题目描述**

[剑指 Offer 05. 替换空格](https://leetcode-cn.com/problems/ti-huan-kong-ge-lcof/)

**思路**

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

**思路二**

可以首先遍历字符串，记录空字符的个数，然后对原始数组婧扩容操作，然后从后先前遍历数组，把所有的字符向后移动，直到遇到空字符添加%20即可，时间复杂度是o(n),空间复杂度是o(1)

